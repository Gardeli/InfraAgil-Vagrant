# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.provision "shell", inline: <<-SHELL

    echo "127.0.0.1 localhost
192.168.70.10 default.dexter.com.br default
192.168.70.11 automation.dexter.com.br automation
192.168.70.12 devops.dexter.com.br devops" > /etc/hosts
    chattr -i /etc/resolv.conf 
    rm -f /etc/resolv.conf
    echo "search dexter.com.br
nameserver 8.8.8.8" > /etc/resolv.conf
    chattr +i /etc/resolv.conf

    mkdir -p /root/.ssh/
    echo "-----BEGIN RSA PRIVATE KEY-----
MIIEowIBAAKCAQEAsJP7W21u5x/31jIJae7xEmzX0COkGnkPnZ4HIjCgoSU0CpdN
YDY122XUowlfcOXSpLy5uS79a2G1+SscqCjUIKjYyiunol5ZPedAjXkK46/bZ84U
vnZooGPaAF1NlynXoGoo4uaeysD1clbTGNiv3kYEYqp2iet7FrlWH3gQ8xdkKRcQ
ZBQCuNTvAtYGB87dSeNMIHVpomyZuv/ZZDYahx+5k24G/SXh/dNmaEe2amPLcsYi
xXvTp9sp+uKG9ZqcVMT2HmHr3x2tsoUMFwDVtG9S63nDlVX+sI8RNlHGPnxTcr0v
d4fgWUwQ6RbTJ4Hvv0mKKDOLHMm3hfOYaW2MnQIDAQABAoIBABrB4eYB2DtnybuI
i4qk7Zz4J1/f9r8YNziQOM6CheTFaXRtZwk8Tb74WFd4VSEbgmb6Pj6Ek1xRSyz9
znLg9PwZ+ffw0480MtvBjjOh8vd7r4i0XspZ0RL07pT9joNokMc7LwTrI4bf5JG1
/HkYZNYO0B1PbXUK3PUdkqJkJFVhpnfPEq7VL7Yczuk3QHQIP0zgwDBmQL8U8B4O
0jWA7uXMT//p1oWyVaYqsxEexcwYXLCPt4X1YJxSlM0eyEfMHxGrmhqZ8nDAVrE0
VRPxUKMS7E+X2A7sE4oUF2lD4B+SuIc85xxw6zmmjC6uvC7UrTomSNIpCWWqKAdL
gWUzRhUCgYEA4pEUIImnLyUk0+LKJIaMuC13JlCkKoCcLWRTE/QkT/vFJeVa62ge
TKNzgyN82DMygFA7Y72ppKG4QiigE3W8qMctx1Q81dOjbB1feVaSFOr0pL+4mBkH
WaXhDR0YWn3Y6ko2F/Dnc558HL6CdpdMtMoa4EPck7T4XFrpp/0nvYMCgYEAx4Ru
n8ojCUO2KcQyF5r3dTm0bVdsX8Ib6+M3p8+FcjXlD5AFlsLDZFy2G9R7gAbUREet
ak6cD6+Rv0fKpq3r88PCIm/RYmGBBjpbQuKANyy8P9QN5M8GYJ+Oc4btcYp7qJ/e
POUaDaVyxWY7TXFhl69qB+RyTWh/4VSNntf0k18CgYBgJflIpaIRW835LXFjdsYZ
ExJRbD9+2f1tNfobqawPVWUg4+hlplXVaDgJGvJMPc3cri/F8CMh/o9XZC4qk/hw
F7bRtGnsxFfB9eUidR6hSeRwVfxcb6Ky5LZQ/lvrayS2qK+0EUPnyQYanK547VRc
FLi7G5FsDYyohNxLsh8/SQKBgHLUZrLyrN2NKg+5yrbJSvkeABkaQtaOKnHGMWcU
yhIksLQXSRAvAjQGJA26amYSCCNQOZ/ApJNmkfTMRfdOjEmc9mPJhXIg+hhyh8nk
ALVAuwvlaSWyfVIpItyc4JYDhQ5VDJxxo2ANRBQWtbTpt6iMnfLy6VJh/Y/bkTLF
yg7zAoGBAIwhvNyXJIcnSe9+2YT+j81lY+iKu5IyuE/kKmkoS7vaWBnfqceWuJKo
HTBpjiTBYL+ZlXcfWJSrNI7HBqeGLjOyJDMtMd7rxqbVksbHxTaEIb1XfV2QtkoU
9T+SF/xm8mZvSh30NZpUrdYFh1pswRYVAtmoANN94hB+k+ae3akZ
-----END RSA PRIVATE KEY-----" > /root/.ssh/id_rsa
    echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCwk/tbbW7nH/fWMglp7vESbNfQI6QaeQ+dngciMKChJTQKl01gNjXbZdSjCV9w5dKkvLm5Lv1rYbX5KxyoKNQgqNjKK6eiXlk950CNeQrjr9tnzhS+dmigY9oAXU2XKdegaiji5p7KwPVyVtMY2K/eRgRiqnaJ63sWuVYfeBDzF2QpFxBkFAK41O8C1gYHzt1J40wgdWmibJm6/9lkNhqHH7mTbgb9JeH902ZoR7ZqY8tyxiLFe9On2yn64ob1mpxUxPYeYevfHa2yhQwXANW0b1LrecOVVf6wjxE2UcY+fFNyvS93h+BZTBDpFtMnge+/SYooM4scybeF85hpbYyd jonathan@jonathan" > /root/.ssh/authorized_keys
    chmod 600 /root/.ssh/id_rsa
  SHELL

# DEFAULT
  config.vm.define "default" do |default|
    default.vm.box = "centos/7"
    default.vm.hostname = "default"
    default.vm.network "private_network", ip: "192.168.70.10", dns: "8.8.8.8"

    config.vm.provider "virtualbox" do |default|
      default.memory = "3072"
    end
  end

# AUTOMATION
  config.vm.define "automation" do |automation|
    automation.vm.box = "ubuntu/bionic64"
    automation.vm.hostname = "automation"
    automation.vm.network "private_network", ip: "192.168.70.11", dns: "8.8.8.8"

    automation.vm.provision "shell", inline: <<-SHELL
      apt install python -y
    SHELL

    config.vm.provider "virtualbox" do |automation|
      automation.memory = "1024"
    end
  end

# DEVOPS
  config.vm.define "devops" do |devops|
    devops.vm.box = "ubuntu/bionic64"
    devops.vm.hostname = "devops"
    devops.vm.network "private_network", ip: "192.168.70.12", dns: "8.8.8.8"

    devops.vm.provision "shell", inline: <<-SHELL
      apt install python -y
    SHELL

    config.vm.provider "virtualbox" do |devops|
      devops.memory = "1024"
    end

  end


end
