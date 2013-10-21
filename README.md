# symfony2-vagrant

Configuración de vagrant para proyectos symfony2 (generada con PuPHPet y personalizada para precise64).

Este repositorio contiene las configuraciones (puppet recipies, Vagrantfile, etc.) que tienes que poner en un proyecto symfony2 para levantar una máquina virtual (ubuntu 12.06) con vagrant y tener la aplicación funcionando en un host virtual de apache.

## Instalación

Instala [virtualbox](https://www.virtualbox.org/) y [vagrant](http://www.vagrantup.com/).

Puedes instalar este repo como un submódulo de git o clonar directamente el repo dentro de tu proyecto symfony2:

Submódulo:

	git submodule add https://github.com/guilu/symfony2-vagrant.git vagrant

o lo clonas directamente:

	git clone https://github.com/guilu/symfony2-vagrant.git vagrant


El fichero `Vagrantfile` debe estar en la raiz del proyecto symfony2 para que todo funcione correctamente, así que puedes sacarlo o crear un enlace symbólico:

	ln -s vagrant/Vagrantfile Vagranfile

A continuación hay varias configuraciones personalizadas con el nombre del proyecto con el que creé la plantilla en [PuPHPet](https://puphpet.com/)


* El nombre de la maquina es `blueboardbox`
* La ip de la máquina virtual es `10.10.10.10`
* El puerto mapeado en host es `8081`
* El directory montado nfs es `/var/www`
* Crea un virtual host en apache `blueboard.dev` para `/var/www/web`
* La base de datos se llama `blueboard` y el password de `root` es `1234`


Edita los ficheros (`Vagrantfile` y `puppet/hieradata/common.yaml`) y modifica los nombres según la configuración de tu proyecto symfony2.

Con los ficheros modificados según tus necesidades ya puedes levantar la máquina

	vagrant up

y ya podrás entrar la máquina virtual con vagrant ssh y trastear lo que quieras.

---