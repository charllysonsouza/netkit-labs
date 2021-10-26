

# Laboratórios do Netkit

Este repositório contêm laboratórios do Netkit para a simulação do funcionamento de protocolos em redes de computadores, em especial, a internet. Através destes podemos verificar o funcionamento de diversos protocolos.

### Configuração e Instalação do Netkit

Para instalar o Netkit são necessários estes arquivos:

* [netkit-2.8.tar.bz2](https://www.netkit.org/assets/netkit/netkit-2.8.tar.bz2)
* [netkit-filesystem-i386-F5.2.tar.bz2](https://www.netkit.org/assets/netkit/netkit-filesystem-i386-F5.2.tar.bz2)
* [netkit-kernel-i386-K2.8.tar.bz2](https://www.netkit.org/assets/netkit/netkit-kernel-i386-K2.8.tar.bz2)

Basta clicar nos links acima para baixar todos os arquivos necessários ou acessar a página do [netkit](https://www.netkit.org/) diretamente.

Você precisa de um computador com Linux, para onde deve baixar os arquivos.

Após baixar os arquivos para o seu computador, descompacte-os dentro de um mesmo subdiretório.

### Configurando a variável de ambiente

Em seguida edite o arquivo __~/.bashrc__ (que contém a configuração do seu shell), e acrescente as seguintes definições de variáveis de ambiente: 

```shell
export NETKIT_HOME=/home/aluno/netkit   

export MANPATH=:$NETKIT_HOME/man 

export PATH=$NETKIT_HOME/bin:$PATH 
```

Obs: no exemplo acima foi assumido que o Netkit está instalado em __/home/aluno__, isto é, você descompactou os arquivos dentro de /home/aluno. Caso tenha instalado-o em um outro diretório você deve fazer a definição correta para a variável de ambiente __NETKIT_HOME__.

### Instalando o shell xterm

O xterm é a aplicação terminal padrão utilizada pelas máquinas virtuais do netkit e sua ausência pode impedir que elas inicializem corretamente. Para distros baseadas em debian utilize o seguinte comando para realizar a instalação via terminal:

```shell
sudo apt-get install xterm
```

### Verificando a instalação

Vá até o diretório onde você descompactou os arquivos, no exemplo, __/home/aluno/netkit__, abra um terminal neste diretório e execute o comando __./check_configuration.sh__. Esse comando irá verificar se tudo está configurado corretamente, e exibirá uma mensagem de __READY__ em caso afirmativo.

```shell
>  Checking path correctness... passed.
>  Checking environment... passed.
>  Checking for availability of man pages... passed.
>  Checking for proper directories in the PATH... passed.
>  Checking for availability of auxiliary tools:
	awk          : ok
	basename     : ok
	date         : ok
	dirname      : ok
	find         : ok
	getopt       : ok
	grep         : ok
	head         : ok
	id           : ok
	kill         : ok
	ls           : ok
	lsof         : ok
	ps           : ok
	readlink     : ok
	wc           : ok
	port-helper  : ok
	tunctl       : ok
	uml_mconsole : ok
	uml_switch   : ok
passed.
>  Checking for availability of terminal emulator applications:
	xterm          : found
	konsole        : not found
	gnome-terminal : found
passed.
>  Checking filesystem type... passed.
>  Checking whether 32-bit executables can run... passed.

[ READY ] Congratulations! Your Netkit setup is now complete!
          Enjoy Netkit!

```

### Iniciando um laboratório

Entre em um do subdiretórios, por exemplo, __netkit-lab_arp__, abra um terminal e execute o comando:

```shell
lstart
```

#### IMPORTANTE!!!

Em cada laboratório há diversos arquivos com a extensão __.startup__. Para que a aplicação inicie as máquinas virtuais corretamente é necessário que para cada arquivo com esta extensão haja uma pasta equivalente com o mesmo nome. Assim, se um laboratório, por exemplo, __netkit-lab_arp__, contiver os arquivos de configurações de hosts e roteadores, pc1.startup, pc2.startup, pc3.startup, r2.startup e r1.startup, será necessário criar uma pasta vazia com o mesmo nome para cada arquivo. Caso contrário, a aplicação exibirá uma mensagem de alerta que não há máquinas virtuais para serem inicializadas.

```shell
=================================================================
Warning: there are no virtual machines to be started.

The lab has been started.
=================================================================
```



