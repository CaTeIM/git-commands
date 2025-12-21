#### 📄 Arquivo: `workflow-pr-limpo.md`

# ✨ Workflow para PR Limpo

Passo a passo padrão para começar uma tarefa, isolar os arquivos e subir para o GitHub.

## 1. Preparação
Garanta que a base está atualizada.
```bash
git checkout master
git pull origin master
```

## 2. Criar Branch

Crie a branch específica para a tarefa.

```bash
git checkout -b fix/nome-descritivo-da-tarefa
# Exemplo: git checkout -b fix/restore-battery-icons
```

## 3. Selecionar Arquivos (Add)

Adicione apenas o necessário. Evite `git add .` se houver arquivos de configuração pessoal.

```bash
git add pasta/arquivo_especifico.ext
# Exemplo: git add main/Kconfig.projbuild
```

## 4. Commit

Crie uma mensagem clara seguindo o padrão (Tipo: Descrição).

```bash
git commit -m "Fix: Descrição clara do que foi resolvido"
```

## 5. Push

Envie a branch para o remoto.

```bash
git push -u origin fix/nome-descritivo-da-tarefa
```