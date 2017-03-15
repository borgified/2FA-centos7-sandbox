This is a sandbox for testing 2FA in CentOS 7.3 based on the excellent guide at [andrewletson.com](https://www.andrewletson.com/set-2fa-centos-server/)

A user called "testuser" with password "testuser" has already been created for you.

To use:

1. download [Vagrant](https://vagrantup.com)
2. git clone https://github.com/borgified/2FA-centos7-sandbox
3. cd 2FA-centos7-sandbox
4. vagrant up --provision

At the end of the provisioning process, the ip of the VM should be revealed to you.

5. ssh <ip of VM> -l testuser
6. yes | google-authenticator
7. exit

And try to ssh back in. If things don't work as expected, you can always `vagrant ssh` to get inside and fix things.

All goes well, you should see:
```
$ ssh 172.16.195.132 -l testuser
Password:
Verification code:
Last login: Wed Mar 15 09:12:59 2017 from 172.16.195.1
[testuser@localhost ~]$
```

If you need to run provisioning again: `vagrant provision`

If you need to start from scratch: `vagrant destroy`
