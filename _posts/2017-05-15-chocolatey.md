## Chocolatey

Não é chato saber que lá na linha de comando do linux posso simplesmente usar o comando 'apt-get' para instalar um programa e suas dependências em minha máquina? Não seria fantástica, e prático, se no meu prompt de comando (cmd) fosse possível usar um programa similar para facilitar minha vida? Pois agora é meu amigo. Esse post vai abrir portas para você.

### Chocolatey o 'apt-get' para Windows

'I'm a tools enabler, I'm a global silent application installer. I configure stuff. Some people want to call me apt-get for Windows, I just want to get #chocolatey!'

Bom, agora vou apresentar um pouco sobre o <a target="_blank" href="https://chocolatey.org/docs">Chocolatey</a> uma ferramenta incrível.

Imagine o cenário, estrou precisando instalar o Ruby na minha máquina, afinal de contas preciso dar manutenção em um blog que usa o <a target="_blank" href="http://jekyllrb.com/">Jekyll</a>. Para isso nada melhor que usar meu mais novo gerenciador de pacotes, o chocolatey.

Como instalar o chocolatey?
Para isso abra o CMD em modo Administrativo (botão direito no menu Iniciar)

```
$ @powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

Como faço para verificar se está instalado? Como abro o help para saber melhor como usá-lo e quais parâmetros posso utilizar?

```
$ choco -?
```

Ok, instalei. Como faço para instalar o ruby?

```
$ choco install ruby -y
```

Nossa, simples assim?
Sim, simples assim.

Como faço para instalar algum outro programa? Por exemplo o Docker?

```
$ choco install docker
```

Hmmm, ainda estou com dúvidas... Como faço para saber quais programas estão disponíveis?
Bom, o chocolatey possui milhares de programas. Para saber quais estão disponíveis o programa conta algumas funcionalidades em seus comandos, por exemplo:

Como faço para listar TODOS os programas?

```
$ choco list
```

Como faço para BUSCAR um programa?

```
$ choco search docker
Chocolatey v0.10.5
boot2docker 1.6.2 [Approved] - Possibly broken
docker 17.05.0 [Approved] Downloads cached for licensed users
docker-for-windows 17.3.1.20170515 [Approved]
docker-toolbox 17.03.1 [Approved] Downloads cached for licensed users
docker-compose 1.13.0 [Approved] Downloads cached for licensed users
docker-machine 0.11.0 [Approved]
docker-machine-vmwareworkstation 1.1.0 [Approved] Downloads cached for licensed users
electron 1.6.2 [Approved] Downloads cached for licensed users
eris 0.12.0 [Approved] Downloads cached for licensed users
gitlab-runner 9.1.1 [Approved]
phpstorm 2017.1.3 [Approved] Downloads cached for licensed users
docker-kitematic 0.17.0 [Approved] Downloads cached for licensed users
kubernetes-kompose 0.6.0 [Approved] Downloads cached for licensed users
kubernetes-cli 1.6.2 [Approved] Downloads cached for licensed users
Minikube 0.18.0 [Approved] Downloads cached for licensed users
minishift 1.0.0 [Approved] Downloads cached for licensed users
nexus-oss 2.14.4.03 [Approved] Downloads cached for licensed users
nexus-repository 3.0.2.02 [Approved] Downloads cached for licensed users
openshift-cli 1.5.0 [Approved] Downloads cached for licensed users
vscode-docker 1.0.0 [Approved]
20 packages found.
```

Rapaz, essa ferramenta pensou em tudo?
Sim, é incrível. Usando o comando 'choco -?' ou 'choco -h' você obtém toda a descrição do que você pode fazer usando esse carinha.

E se eu quiser desinstalar um programa? Como faço?

```
$ choco uninstall docker
```

Realmente o chocolatey é um programa incrível, e realmente pode ser considerado o 'apt-get' do Windows.
