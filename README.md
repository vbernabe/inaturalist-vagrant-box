# inaturalist-vagrant-box
This is a complete vagrant box which includes all dependencies for iNaturalist Web App

### Download Vagrant Box
```sh
https://www.dropbox.com/s/l8yphbwnhszlce6/inaturalist.box?dl=0
```

### Provision the Vagrant box
```sh
$ mkdir inaturalist-box
$ cd inaturalist-box
$ cp path-to-downloaded-file/inaturalist.box ./
$ vagrant box add inaturalist-base inaturalist.box
$ vagrant init inaturalist-base
$ vagrant up
$ vagrant ssh
```

### Clone iNaturalist Repo inside your Vagrant box
```sh
$ git clone https://github.com/inaturalist/inaturalist.git
```
### Configure iNaturalist
```ssh
$ cd inaturalist/
$ gem install rake -v '10.5.0'
$ bundle install
$ rake es:start
$ cp config/config.yml.example config/config.yml
$ cp config/database.yml.example config/database.yml
$ cp config/gmaps_api_key.yml.example config/gmaps_api_key.yml
$ cp config/smtp.yml.example config/smtp.yml
$ cp config/secrets.yml.example config/secrets.yml
$ bin/rake db:migrate RAILS_ENV=development
$ rails g airbrake 1234 09af09af09af09af09af09af09af09af09af09af
$ rails generate airbrake --api-key 09af09af09af09af09af09af09af09af09af09af
$ vi /home/vagrant/inaturalist/config/database.yml
  Add the following
	username: postgres
	password: secret123
```

### Start iNaturalist
```sh
$ rails s -b 192.168.33.51
```

### Access iNaturalist on your browser
```sh
http://192.168.33.51:3000
```
