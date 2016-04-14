# inaturalist-vagrant-box
This is a complete vagrant box which includes all dependencies for iNaturalist Web App

### Clone Repository
```sh
$ git clone https://github.com/vbernabe/inaturalist-vagrant-box.git inaturalist-box
```

### Provision box
```sh
$ cd inaturalist-box
$ vagrant box add inaturalist-base inaturalist.box
$ vagrant init inaturalist-base
$ vagrant up
$ vagrant ssh
```

### Clone iNaturalist Repo inside your Vagrant box
```sh
$ git clone https://github.com/inaturalist/inaturalist.git
```

### Start iNaturalist
```sh
$ cd inaturalist/inaturalist-master/
$ rake es:start
$ rails s -b 192.168.33.51
```
