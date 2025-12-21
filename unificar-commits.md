#### 📄 Arquivo: `unificar-commits.md`

# 🧹 Unificar Commits (Squash)

Use isso quando você tem vários commits pequenos ("fix", "typo", "wip") e quer transformar tudo em um único commit profissional antes de pedir Review.

## 1. Check de Segurança (Onde eu estou?)

Antes de qualquer coisa, garanta que você está na branch que quer limpar.

```bash
git branch

```

* **Olhe o asterisco (`*`).**
* Se estiver na `master`, **PARE**. Você não quer reescrever a master.
* Se estiver na sua branch de feature (ex: `fix/tdisplay-power`), siga em frente.

**Se precisar trocar:**

```bash
git checkout fix/nome-da-sua-branch

```

## 2. Diagnóstico (Quantos voltar?)

Veja o histórico recente para decidir quantos commits você precisa fundir.

```bash
git log --oneline

```

**Exemplo de Saída:**

```text
e5f6g7h (HEAD) Fix: Remove debug print  <-- Commit Novo (lixo)
a1b2c3d Fix: Adjust float logic         <-- Commit Novo (lixo)
890k1l2 Feat: Add battery support       <-- Commit Principal (que vai ficar)
z5y4x3w Merge pull request...           <-- Histórico antigo (LIMITE)

```

**Conta:** Você tem 1 principal + 2 correções acima dele. Total de commits para mexer: **3**.

## 3. O Comando (Abrindo a Cirurgia)

Inicie o modo interativo indicando o número total de commits (`N`) que você contou acima.

```bash
git rebase -i HEAD~3

```

*(Lê-se: "Quero editar interativamente os últimos 3 commits da cabeça dessa branch")*

## 4. A Edição (O Pulo do Gato)

O editor de texto vai abrir (Nano ou Vim). Você verá algo assim:

```text
pick 890k1l2 Feat: Add battery support
pick a1b2c3d Fix: Adjust float logic
pick e5f6g7h Fix: Remove debug print

```

**A Regra:**

* **`pick`**: Mantém o commit. (Deixe sempre o **primeiro** da lista como `pick`).
* **`fixup`** (ou `f`): Funde com o de cima e **apaga** a mensagem de log.
* **`reword`** (ou `r`): Mantém o commit, mas deixa você editar a mensagem (útil se o commit principal estiver com erro de digitação).

**Como deve ficar (Edite o texto):**

```text
pick 890k1l2 Feat: Add battery support
fixup a1b2c3d Fix: Adjust float logic
fixup e5f6g7h Fix: Remove debug print

```

## 5. Salvar e Sair

* **No Nano:** `Ctrl+O` (Enter para salvar) -> `Ctrl+X` (Sair).
* **No Vim:** Esc -> `:wq` -> Enter.

*Se der tudo certo, o Git dirá: `Successfully rebased...*`

## 6. O Envio (A Força)

Agora seu histórico local está limpo (1 commit), mas o GitHub ainda tem o histórico sujo (3 commits). O Git vai bloquear um push normal. Você precisa impor sua nova realidade.

```bash
git push origin fix/nome-da-sua-branch --force

```

**Resultado:** O Pull Request no GitHub atualiza magicamente para mostrar apenas **um** commit perfeito. 🏆