# Passo a passo para criar o comando "git clean-branches" 
Este é um passo a passo para configurar o Git Bash e agilizar a limpeza das branches locais, exceto a "main"

## Instalando o Visual Studio Code (caso não possuir)

1. Acesse o site oficial do Visual Studio Code em https://code.visualstudio.com/.
2. Clique no botão "Download" para baixar o instalador do VS Code.
3. Execute o instalador e siga as instruções para concluir a instalação.

## Configurando o Git Bash para abrir arquivos com o Visual Studio Code

1. Abra o terminal Git Bash.
2. Digite o seguinte comando para definir o VS Code como editor padrão do Git Bash:
```bash
git config --global core.editor 'code --wait'
```
3. Feche e abra o Git Bash para as novas configurações serem carregadas

## Criando o alias "clean-branches"

1. Abra o terminal Git Bash.
2. Digite o seguinte comando para abrir o arquivo de configuração global do Git:
```bash
git config --global --edit
```
3. No arquivo de configuração que será aberto, adicione as seguintes linhas:
```bash
[alias]
  clean-branches = "!git checkout main && git branch | grep -v "main" | xargs git branch -D"
```
Obs: Caso seu repositório utilize a branch principal como "master" ou algum outro nome, substituir o "main" do comando acima pelo nome que seu repositório utilizar.

4. Salve e feche o arquivo de configuração.
5. Feche e abra o Git Bash para as novas configurações serem carregadas.
6. Agora, sempre que precisar limpar todas as branches locais, exceto a "main", basta digitar o comando:
```bash
git clean-branches
```



