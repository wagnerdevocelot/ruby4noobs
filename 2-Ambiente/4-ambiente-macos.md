
## 2.4 Ambiente MacOS

  
Em algumas versões do MacOs o Ruby já vem instalado por padrão então se quiser tirar essa dúvida de inicio basta digitar no terminal

```bash
ruby --version
```
Se ele indicar a versão já está na sua maquina, caso não tenha instalado ou queira usar uma verão mais recente basta seguir com o tutorial.

Para o ambiente MacOS, utilizaremos uma ferramenta chamada Homebrew para instalar o Ruby.

  

Homebrew é um gerenciador de pacotes open-source que simplifica a instalação de uma grande variedade de softwares no ambiente MacOS e Linux.



## Passo a passo:

  

- Instale o Homebrew executando o seguinte comando em seu terminal (para mais informações: https://brew.sh/):

  

```bash

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

```

  

- Caso o passo anterior for executado com sucesso, poderá executar o comando:

  

```bash

$ brew -v

  

# Resultado esperado

Homebrew 2.7.5 # Ou qualquer outra versão

```

  

- Se desejar instalar a versão do Ruby mais recente suportada pelo homebrew, basta executar o seguinte comando:

  

```bash

# Para installar a versão mais recente

brew install ruby
```

- Se todos os passos anteriores foram executados com sucesso, o Ruby já está instalado em sua máquina.

Para testá-lo, pode executar o seguinte comando no seu terminal:


```bash
ruby --version
```
Para mais informações sobre como instalar o Ruby utilizando homebrew no MacOS:

  
https://www.ruby-lang.org/pt/documentation/installation/#homebrew

