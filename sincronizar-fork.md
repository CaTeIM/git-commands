### 📄 Arquivo: `sincronizar-fork.md`

# 🔄 Sincronizar Fork (Rebase)

Passo a passo para atualizar seu fork com o repositório original (`upstream`) mantendo o histórico linear.

⚠️ **IMPORTANTE:** Não clique no botão "Update branch" da interface do GitHub. Ele cria commits de merge desnecessários.

## Procedimento

1. **Baixar atualizações do original:**
   ```bash
   git fetch upstream
```

2. **Aplicar Rebase (seus commits vão para o topo):**
```bash
git rebase upstream/master
```


3. **Enviar para o seu GitHub (Force Push):**
```bash
git push origin master --force
```