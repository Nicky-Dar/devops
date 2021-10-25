Set the network from NAT to Bridge

![image](https://user-images.githubusercontent.com/88620315/138304900-33007231-a991-4aec-96e9-d7e78c4b059b.png)

![image](https://user-images.githubusercontent.com/88620315/138304965-b9647230-43f4-467c-b5f3-8af5132623cc.png)
Configure Static IP Address

>cd /etc/netplan/
>ls
>sudo nano 00-installer-config.yaml

![image](https://user-images.githubusercontent.com/88620315/138377048-b357a197-6ab7-40a8-a77e-24111d5765f7.png)

You can config your static address here
![image](https://user-images.githubusercontent.com/88620315/138378741-651c811c-4e8c-4d2b-9bf8-ce03209bbf53.png)

Sample static IP address:
> network:

>     ethernets:

>         enp0s3:

>             addresses: [192.168.1.2/24]

>             gateway4: 192.168.1.1

>             nameservers:

>               addresses: [8.8.8.8,8.8.4.4]

>             dhcp4: no

>     version: 2	


Keterangan:
* enp0s3: nama network interface, cara mengecek namanya pakai perintah ip addr.
* addresses: IP address yang diberikan dengan subnet /24 (255.255.255.0).
* nameservers – addresess: IP address untuk dns resolver, di sini memakai DNS dari Google.
* dhcp4: diisi dengan no jika tidak memakai DHCP. Jika memakai DHCP, semua IP address tidak usah dimasukkan.


Activate the newly created IP address configuration.
>sudo netplan apply

![image](https://user-images.githubusercontent.com/88620315/138380531-a82f6722-778c-4382-953a-9869b587d6be.png)

make remote connection
>ssh [user]@[ip address]

![image](https://user-images.githubusercontent.com/88620315/138392320-ce5dc7fd-52ff-431b-8900-843f0c310be0.png)

