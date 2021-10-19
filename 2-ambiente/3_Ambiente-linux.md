## 2.3 Ambiente Linux

Por ser uma linguagem open source, em quase todos os sistemas linux o ruby já vem instalado por padrão. Para verificar se seu sistema já tem o ruby instalado, abra o terminal digitando `ctrl + alt + t` e digite:

```bash
$ ruby -v
```
Vai aparecer algo mais ou menos parecido com isso:
```
$ ruby 3.0.1p64 (2021-04-05 revision 0fb782ee38) [x86_64-linux]
```

Caso você queira instalar uma outra versão do Ruby, então utilize algum gerenciador para ficar mais fácil alternar entre as versões quando desejar, inclusive atualizar de forma mais simples e rápida.

### Rbenv

Rbenv é uma ferramenta de gerenciamento de versões do ruby, com esse gerenciador é possível instalar múltiplas versões do Ruby na sua máquina.

* Primeiramente, você deve atualizar os pacotes e instalar as dependencias:
> * Ubuntu/Debian:
```bash
$ sudo apt-get update
$ sudo apt-get install autoconf bison build-essential libssl-dev libyaml-dev libreadline6-dev zlib1g-dev libncurses5-dev libffi-dev libgdbm3 libgdbm-dev
$ sudo apt-get install git
```

> * Fedora/CentOS
```bash
$ yum install git-core zlib zlib-devel gcc-c++ patch readline readline-devel libyaml-devel libffi-devel openssl-devel make bzip2 autoconf automake libtool bison curl sqlite-devel
```
* Em seguida, baixe o rbenv do repositório para sua máquina com o seguinte comando:
```bash 
$ curl -fsSL https://github.com/rbenv/rbenv-installer/raw/HEAD/bin/rbenv-installer | bash
```
* Depois, adicione `~/.rbenv/bin` ao seu `$PATH` assim você pode usar os comandos do `rbenv`.
```bash
$ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
```

* Depois, adicione o comando eval "$(rbenv init -)" no seu arquivo  ~/.bashrc que assim o `rbenv` pode vai automaticamente

```bash
$ echo 'eval "$(rbenv init -)"' >> ~/.bashrc
```

* Em seguida, aplique as mudanças que você efetou na sua sessão atual do bash:
```bash
$ source ~/.bashrc
```

* Se tudo estiver certo, ao rodar o seguinte comando
```bash
$ type rbenv
```

Algo parecido com isso vai aparecer pra você
```bash
rbenv is a function
rbenv ()
{
    local command;
    command="${1:-}";
    if [ "$#" -gt 0 ]; then
        shift;
    fi;
    case "$command" in
        rehash | shell)
            eval "$(rbenv "sh-$command" "$@")"
        ;;
        *)
            command rbenv "$command" "$@"
        ;;
    esac
}
```

Agora, vamos instalar o `ruby-build`. É ele que vai ficar encarregado de instalar o `rbenv install` para que você consiga instalar as versões que quiser na sua máquina.
* Clone o repo para sua máquina
 ```bash
 $ git clone https://github.com/rbenv/ruby-build.git
```

* Depois, utilize o seguinte comando para instalar:
```bash
$ PREFIX=/usr/local sudo ./ruby-build/install.sh
```

Pronto. A partir daqui você já tem tanto o rbenv quanto o ruby-build instalados. Agora vamos para o próximo passo.

#### Instalando o Ruby
Uma vez que você tenha o rbenv instalado, você conseguirá visualizar uma lista de versões prontas para serem instaladas.

```bash
$ rbenv install -l
```

Vai aparecer no seu terminal algo parecido com isso:
```bash
2.6.8
2.7.4
3.0.2
jruby-9.2.19.0
mruby-3.0.0
rbx-5.0
truffleruby-21.1.0
truffleruby+graalvm-21.1.0

Only latest stable releases for each Ruby implementation are shown.
Use 'rbenv install --list-all / -L' to show all local versions.
```

Agora, instale sua versão desejada que aparece na lista, no caso a 3.0.2, a ultima versão estável atualmente:
```bash
$ rbenv install 3.0.2
```

Aguarde a instalação e siga todos os passos, pode demorar um pouco. Após isso, configure a versão instalada como a versão padrão do seu sistema, com o comando `global`
```bash
$ rbenv global 3.0.2
```

Em seguida, rode o seguinte comando para verificar se tudo ocorreu como planejado
```bash
$ ruby -v
```

Vai aparecer algo mais ou menos parecido com isso:
```
$ ruby 3.0.2p107 (2021-07-07 revision 0db68f0233) [x86_64-linux]
```

Percebe-se que no inicio desses passos a versão era a 3.0.1, e agora a versão é a 3.0.2

Se você chegou até aqui com tudo certo, então pode prosseguir!

Ir para: [2.4 Ambiente MacOs](4_Ambiente-macos.md)
