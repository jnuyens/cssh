# cssh
Clustered ssh - puppet based command launching 

From the puppet server, you can launch with cssh, cscp and csshsudo different commands to be launched on all or a part of the servers in your infrastructure.

cssh, cscp and csshsudo look at the /etc/puppet/manifests/site.pp file to determine on which machines the ssh command needs to be run.
It is run one by one. This means it will not be super-fast, but has more feedback and less problems associated with it than solutions which perform everything in parrallel.
This means it is suited for medium sized environments with less than about 500 servers.
For 10s of thousands servers, it's probably not the best solution.

By default it recognises the roles: all, dev (for the development servers), stg (staging) and prd (for production). But you can adapt these scripts easily depending upon your needs.

We advise that you enable ssh keyfiles to enable passwordless execution of the commands from the puppet server.
