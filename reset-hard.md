# Git Reset Hard 🧨

O comando `git reset --hard` é uma ferramenta poderosa (e perigosa) usada para descartar alterações e redefinir o estado do seu repositório.

## O que ele faz?

1.  **Move o ponteiro HEAD**: Aponta a sua branch atual para um commit específico.
2.  **Atualiza o Index (Staging Area)**: Iguala o index ao commit selecionado.
3.  **Atualiza o Diretório de Trabalho (Working Directory)**: **Sobrescreve** todos os arquivos no seu diretório de trabalho para corresponderem ao commit selecionado.

> [!WARNING]
> **Cuidado!** Qualquer alteração local que não tenha sido commitada será **PERDIDA PERMANENTEMENTE**. Use com cautela.

## Casos de Uso Comuns

### 1. Descartar alterações locais não commitadas

Se você fez várias alterações, bagunçou tudo e quer voltar exatamente para como estava no último commit:

```bash
git reset --hard HEAD
```

### 2. Voltar para um commit anterior (apagando o histórico posterior)

Se você quer "voltar no tempo" e apagar tudo o que foi feito após um certo ponto:

```bash
git reset --hard <hash-do-commit>
```

_Exemplo: `git reset --hard a1b2c3d`_

### 3. Sincronizar com a branch remota (descartando changes locais)

Se você quer que sua branch local fique exatamente igual à remota (origin/main), ignorando qualquer mudança local:

```bash
git fetch origin
git reset --hard origin/main
```
