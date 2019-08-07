# ubuntu_r8169
ethernet controller driver issue

Once you install a ubuntu on the computer, you have to check the model of the lan card and install the driver to connect the internet. 
You can check the hardware info by typing the following commmand.

```console
$ lspci 
```

If you see the name "r8169" on the network/ethernet controller info, you're in trouble. 
Many users suffer from installing a proper driver of lan card "r8169" or using internet with it. 

To solve the problem, you need to disable r8169 driver and install a r8168 driver. 

1. Adding the previous driver on the blacklist.

```console 
$ echo "blacklist r8169" >> /etc/modprobe.d/blacklist.conf
```

2. Installing the r8168 driver

To install the driver, 'make' command is neccessary. However, we have neither 'make' nor internet connection. 
Download debian file of make program and install it using the following command. 

```console
$ sudo dpkg -i /path/name_of_file.deb
```

To install the make.deb file, additional packages that are not on the computer are needed, such as specific version of gcc. 

I downloaded every neccessary files and installed it. 

Using uploaded files, I hope you can also install the network driver. :)


References : 

https://tosavetheworld.tistory.com/entry/%EC%9A%B0%EB%B6%84%ED%88%AC-%EC%84%9C%EB%B2%84-%EB%B2%84%EC%A0%84-%EC%84%A4%EC%B9%98-%EB%9E%9C%EC%B9%B4%EB%93%9C-%EB%93%9C%EB%9D%BC%EC%9D%B4%EB%B2%84-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0

http://egloos.zum.com/mcchae/v/10795420
