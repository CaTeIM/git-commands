# Git Commands 🛠

Repositório pessoal de documentação para comandos e workflows essenciais do Git.

## Índice

1. **[Sincronizar Fork (Rebase)](sincronizar-fork.md)**
   - Como atualizar seu fork com o repositório original mantendo o histórico linear e limpo.

2. **[Workflow de PR Limpo](workflow-pr-limpo.md)**
   - Passo a passo para criar uma branch, commitar e subir alterações de forma organizada.

3. **[Unificar Commits (Squash)](unificar-commits.md)**
   - Como transformar vários commits pequenos em um único commit profissional antes do PR.

4. **[Limpeza Pós-Merge](limpeza-pos-merge.md)**
   - Como apagar branches antigas e limpar referências para economizar espaço e manter a organização.

### Os tipos principais:

O padrão da indústria é o **Conventional Commits**. Ele estrutura a mensagem para facilitar leitura humana e automação (changelogs).

A estrutura básica é: `tipo(escopo): descrição curta`

* ✨ **`feat`** (Feature): Criação de uma nova funcionalidade.
*Ex: `feat(login): adiciona suporte a 2FA*`

* 🐛 **`fix`** (Fix): Correção de um bug.
*Ex: `fix(api): corrige erro 500 no endpoint de usuários*`

* 📚 **`docs`** (Documentation): Alterações apenas na documentação (README, Wiki).
*Ex: `docs: atualiza instruções de instalação*`

* 💄 **`style`** (Style): Formatação, espaços, ponto-e-vírgula (não altera lógica de código).
*Ex: `style: remove espaços em branco extras*`

* ♻️ **`refactor`** (Refactoring): Alteração no código que não corrige bug nem adiciona feature (melhoria de estrutura).
*Ex: `refactor(auth): simplifica lógica de validação de token*`

* ⚡ **`perf`** (Performance): Mudança de código para melhorar desempenho.
*Ex: `perf(db): adiciona index na tabela de logs*`

* 🧪 **`test`** (Test): Adição ou correção de testes.
*Ex: `test: adiciona testes unitários para controller de vendas*`

* 🔧 **`chore`** (Chore): Atualizações de tarefas de build, configurações de ferramentas (não altera código de produção).
*Ex: `chore: atualiza versão do node no dockerfile*`

* 📦 **`build`**: Alterações que afetam o sistema de build ou dependências externas (npm, maven, gradle).
*Ex: `build(deps): atualiza react para v18*`

* 👷 **`ci`**: Alterações em arquivos de configuração de CI (GitHub Actions, Travis, CircleCI).
*Ex: `ci: corrige pipeline de deploy*`

* ⏪ **`revert`**: Reverte um commit anterior.
*Ex: `revert: feat(header): remove botão de busca*`

### Regras Rápidas:

1. **Use o imperativo:** "adiciona" em vez de "adicionado" ou "adicionei".
2. **Letra minúscula:** Comece a descrição com minúscula.
3. **Breaking Change:** Se a mudança quebra compatibilidade, adicione `!` após o tipo ou `BREAKING CHANGE:` no rodapé.
* *Ex: `feat(api)!: remove suporte a v1 da API*`