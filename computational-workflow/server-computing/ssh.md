# ssh

**Secure Shell** \(**ssh**\) is a protocol used to securely log onto remote systems. It is the most common way to access remote Linux and Unix-like servers. In the Salis lab, you will likely need to connect to the original "Salis Webserver" \(Dell XPS\), our compute cluster \(`spartacus`\), any number of available high-performance-computing \(HPC\) systems at our disposal \(e.g. Texas Advanced Computing Center\), and/or cloud computing resources \(e.g. Amazon Web Services \(AWS\)\) to run model predictions or simulations. `ssh` is your go-to tool to connect to these computing resources, no matter where you are! The following describes how to connect to our servers from either Windows or Linux \(for MacOS follow the Linux instructions\).

Note: Email Dr. Salis to receive a username, password, and the IP address for the lab's computing resources.

### Connecting to the COE-VPN

If you are trying to remotely access servers located within the College of Engineering \(COE\) network \(e.g. the `XPS` server in lab\), you'll need to connect to the COE Virtual Private Network \(COE-VPN\). The software is constantly changing, so you'll need to find what the current client is and how to install it. Download the software and login with your student access ID and password. To find the client, google "COE VPN PSU" or try this link: [http://www.ncts.psu.edu/vpn/index.aspx](http://www.ncts.psu.edu/vpn/index.aspx). No promise that link still works. Currently, we are using the `Global Protect` client.

## Windows

Within Windows, you'll need to use an SSH Client. Here are a few I've used:

**SSH Secure Shell** \| Click "Quick Connect". Paste in the server IP-address under "Host Name". Put your username in the "User Name" field. Click connect. You will be prompted to provide your password to login. Because you read up on [Linux](https://github.com/reisalex/salis-lab-protocol-book/tree/453898c9360786eef221e6fffd8409c03a547e50/02_Server_Computing/01_Linux/README.md), you can immediately start typing some commands in!

**MobaXterm** \| Click Session &gt; SSH, and fill in host and username as described above. You can save sessions so that you don't need to remember the IP-addresses.

Note: In many cases, depending on what network you are on, you won't be able to directly connect to `spartacus1` because it has an IPv6 address. In Windows, to connect to `spartacus1`, I connect to the `XPS` server located in lab, and from that ssh session, ssh again into `spartacus1`. If you need to do this, I recommend you read up on Linux ssh below.

## Linux

Linux ssh is much more simple. Open up the terminal, and write `ssh` followed by the address name!

```text
$ ssh alex@188.85.194.223
```

This command would login to the user `alex` on the server with address `188.85.194.223`. On my own machine, my local user is also conveniently `alex`, so I actually can just write:

```text
$ ssh 188.85.194.223
```

To obtain the same outcome. Of course, the server will prompt you for your password. Type it in, hit Enter, and you're good to go.

When you login to a server for the first time from a linux machine, you'll be prompted to "authenticate" or "allow" the connection. Just write "yes" or "Y" and hit Enter.

```text
The authenticity of host '188.85.194.223 (188.85.194.223)' can't be established.
RSA key fingerprint is SHA256:7jmnAjNhm47ijc5rnfozuyCfyESxg0sOIAk7VqZIHxc.
Are you sure you want to continue connecting (yes/no)?
```

And you're good to go!

### Creating a server alias

Now, if you're like me and you don't like memorizing IP addresses, you probably want a way to save the server address and even link it to an easy-to-remember alias. Don't worry `ssh` protocol has got you covered. Complete the following steps:

Navigate home. Create a subdirectory `.ssh` using `mkdir`. Open up a file named `config` in that directory. Here I'm using the command `subl` which calls Sublime Text, my preferred text editor for code, markup and prose:

```text
$ cd ~
$ mkdir .ssh
$ subl .ssh/config
```

Within this file, you can add hosts as needed. There are numerous help pages that describe all the different options, however, I find the following settings are sufficient. Nicknames for the hosts are up to you! I recommand short, memorable words, so that it is easy to login via CL.

```text
Host fakeserver
   HostName 188.85.194.223
   User alex
   ServerAliveInterval 120
   ServerAliveCountMax 30
```

Save the `config` file. Now try `ssh` with the new alias.

```text
$ ssh fakeserver
```

### Teredo tunneling with miredo

On linux machines, we are currently using Teredo IPv6 tunneling services to connect to the IPv6 world from the IPv4 one. Maybe someday everything will be IPv6, or maybe IPv4 will more naturally communicate with IPv6. Specifically, on Ubuntu-derived distros, we have been using `miredo`. You'll need to install this if you want to connect directly to `spartacus1`. The `XPS` server in lab has this installed, and this is how it communicates with `spartacus1`. In the terminal install using the following:

```text
$ sudo apt-get install miredo
```

You should be good to go.

### Transfering files to-and-from a remote server with scp

To transfer a file _to_ a directory on a remote server type the following:

```text
$ scp path/to/myfile.txt alex@188.85.194.223:~/destination/file/location
```

To download a file _from_ a remote server and rename it, type the following:

```text
$ scp alex@188.85.194.223:~/destination/file/location/myfile.txt path/to/myfile_from_server.txt
```

And if you have an alias for your server defined in `config`:

```text
$ scp spartacus:~/path/to/file.txt path/to/my/file.txt
```

Google around for more usage directions, but this is about it! Use the `-r` flag if you're trying to transfer a directory with contents in it.

