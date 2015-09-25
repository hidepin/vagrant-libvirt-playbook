# vagrant-libvirt-playbook

vagrant-libvirt setup
------------------------------------------------------------
usermod -a -G libvirt (ユーザ名)
usermod -a -G vboxusers (ユーザ名)

1.vagrant plugin install
    ```
    vagrant plugin install vagrant-libvirt
    vagrant plugin install vagrant-mutate
    ```

vagrant-libvirtの参考手順
------------------------------------------------------------
1. boxを追加
    ```
    vagrant box add opscode-centos-6.5 http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-6.5_chef-provisionerless.box
    ```

2. vagrant-libvirtで起動
    ```
    vagrant init opscode-centos-6.5

vagrant mutate opscode-centos-6.5 --input-provider virtualbox libvirt
    vagrant up --provider=libvirt
    ```

[root@vagrant ~]# KERN_DIR=/usr/src/kernels/`uname -r`
[root@vagrant ~]# KERN_DIR=/usr/src/kernels/3.10.0-229.14.1.el7.x86_64/
[root@vagrant ~]# /etc/init.d/vboxdrv setup
