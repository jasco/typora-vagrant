# Typora Markdown editor vagrant box

[Typora](https://typora.io) is an unaffiliated Markdown editor.

    vagrant up
    ./start

The `shared_data` subdirectory will be mounted as `/home/vagrant/shared_data` in the container.

`start` uses X11 to open the markdown editor in the host.  For recent version
of MacOS install `xquartz` to get X11 functionality.

