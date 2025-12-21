### 📄 Arquivo: `unificar-commits.md`

# 🧹 Unificar Commits (Squash)

Use isso quando tiver vários commits pequenos ("fix", "typo", "wip") e quiser transformar tudo em um único commit sólido antes de pedir Review.

## 1. Check de Segurança
Garanta que está na branch correta (nunca faça isso na `master`).

```bash
git branch
# Se estiver na sua branch de feature (ex: fix/nome-da-branch), siga em frente.
```

## 2. Diagnóstico (Quantos voltar?)

Veja o histórico para decidir quantos commits fundir.

```bash
git log --oneline
```

*Conte quantos commits novos (lixo/wip) existem acima do commit principal ou do último merge.*

## 3. O Comando

Inicie o modo interativo (`N` = número de commits para editar).

```bash
git rebase -i HEAD~N
# Exemplo para os últimos 3 commits: git rebase -i HEAD~3
```

## 4. A Edição

O editor abrirá. Use esta lógica:

* **1ª linha:** Mantenha `pick` (este será o commit base).
* **Linhas seguintes:** Mude `pick` para `fixup` (ou `f`). Isso funde com o de cima e apaga o log extra.

**Exemplo:**

```text
pick 890k1l2 Feat: Add battery support
fixup a1b2c3d Fix: Adjust float logic
fixup e5f6g7h Fix: Remove debug print
```

Salve e saia (`Ctrl+O` -> `Enter` -> `Ctrl+X` no Nano).

## 5. O Envio (Force Push)

Como você reescreveu o histórico local, o GitHub vai rejeitar um push normal. Force a atualização:

```bash
git push origin fix/nome-da-sua-branch --force
```
