#### 📄 Arquivo: `limpeza-pos-merge.md`

# 🗑️ Limpeza Pós-Merge

Execute após o seu PR ser aprovado e mergeado na master. Isso evita o acúmulo de lixo local e economiza armazenamento.

## 1. Atualizar a Master
Volte para a base e garanta que ela tem a versão final do seu código.
```bash
git checkout master
git pull origin master
```

## 2. Deletar Branches Locais

Delete as branches de feature que já foram integradas.

```bash
git branch -D fix/nome-da-branch-antiga
# Exemplo: git branch -D fix/restore-battery-icons
```

## 3. Faxina Geral

Limpe referências remotas que não existem mais (branches deletadas no servidor).

```bash
git fetch --prune
```