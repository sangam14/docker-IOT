# docker-IOT

```
Biradars-Air-2:~ sangam$ docker run -ti --privileged node /bin/bash
Unable to find image 'node:latest' locally
latest: Pulling from library/node
c5e155d5a1d1: Pull complete 
221d80d00ae9: Pull complete 
4250b3117dca: Pull complete 
3b7ca19181b2: Pull complete 
425d7b2a5bcc: Pull complete 
69df12c70287: Pull complete 
9b754a1bcda7: Pull complete 
74b273083e97: Pull complete 
Digest: sha256:3d4411d1933dc93e78b9e0de556a22178269952b98cbbea7ca935d890527ae27
Status: Downloaded newer image for node:latest
root@14801ba53858:/# mkdir test && cd test
root@14801ba53858:/test# npm install johnny-five

> @serialport/bindings@2.0.8 install /test/node_modules/@serialport/bindings
> prebuild-install --tag-prefix @serialport/bindings@ || node-gyp rebuild

npm WARN saveError ENOENT: no such file or directory, open '/test/package.json'
npm notice created a lockfile as package-lock.json. You should commit this file.
npm WARN enoent ENOENT: no such file or directory, open '/test/package.json'
npm WARN test No description
npm WARN test No repository field.
npm WARN test No README data
npm WARN test No license field.

+ johnny-five@1.1.0
added 95 packages from 55 contributors and audited 303 packages in 20.844s
found 0 vulnerabilities

root@14801ba53858:/test# apt-get update && apt-get install -y vim
Ign:1 http://deb.debian.org/debian stretch InRelease
Get:2 http://deb.debian.org/debian stretch-updates InRelease [91.0 kB]
Get:3 http://security.debian.org/debian-security stretch/updates InRelease [94.3 kB]        
Get:4 http://deb.debian.org/debian stretch Release [118 kB]                                 
Get:5 http://deb.debian.org/debian stretch-updates/main amd64 Packages [31.7 kB]         
Get:6 http://security.debian.org/debian-security stretch/updates/main amd64 Packages [492 kB]
Get:7 http://deb.debian.org/debian stretch Release.gpg [2434 B]               
Get:8 http://deb.debian.org/debian stretch/main amd64 Packages [7082 kB]
Fetched 7912 kB in 18s (417 kB/s)                                                                                                             
Reading package lists... Done
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following additional packages will be installed:
  libgpm2 vim-common vim-runtime xxd
Suggested packages:
  gpm ctags vim-doc vim-scripts
The following NEW packages will be installed:
  libgpm2 vim vim-common vim-runtime xxd
0 upgraded, 5 newly installed, 0 to remove and 3 not upgraded.
Need to get 6766 kB of archives.
After this operation, 31.2 MB of additional disk space will be used.
Get:1 http://deb.debian.org/debian stretch/main amd64 xxd amd64 2:8.0.0197-4+deb9u1 [132 kB]
Get:2 http://deb.debian.org/debian stretch/main amd64 vim-common all 2:8.0.0197-4+deb9u1 [159 kB]
Get:3 http://deb.debian.org/debian stretch/main amd64 libgpm2 amd64 1.20.4-6.2+b1 [34.2 kB]
Get:4 http://deb.debian.org/debian stretch/main amd64 vim-runtime all 2:8.0.0197-4+deb9u1 [5407 kB]
Get:5 http://deb.debian.org/debian stretch/main amd64 vim amd64 2:8.0.0197-4+deb9u1 [1034 kB]                                                 
Fetched 6766 kB in 10s (625 kB/s)                                                                                                             
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package xxd.
(Reading database ... 29980 files and directories currently installed.)
Preparing to unpack .../xxd_2%3a8.0.0197-4+deb9u1_amd64.deb ...
Unpacking xxd (2:8.0.0197-4+deb9u1) ...
Selecting previously unselected package vim-common.
Preparing to unpack .../vim-common_2%3a8.0.0197-4+deb9u1_all.deb ...
Unpacking vim-common (2:8.0.0197-4+deb9u1) ...
Selecting previously unselected package libgpm2:amd64.
Preparing to unpack .../libgpm2_1.20.4-6.2+b1_amd64.deb ...
Unpacking libgpm2:amd64 (1.20.4-6.2+b1) ...
Selecting previously unselected package vim-runtime.
Preparing to unpack .../vim-runtime_2%3a8.0.0197-4+deb9u1_all.deb ...
Adding 'diversion of /usr/share/vim/vim80/doc/help.txt to /usr/share/vim/vim80/doc/help.txt.vim-tiny by vim-runtime'
Adding 'diversion of /usr/share/vim/vim80/doc/tags to /usr/share/vim/vim80/doc/tags.vim-tiny by vim-runtime'
Unpacking vim-runtime (2:8.0.0197-4+deb9u1) ...
Selecting previously unselected package vim.
Preparing to unpack .../vim_2%3a8.0.0197-4+deb9u1_amd64.deb ...
Unpacking vim (2:8.0.0197-4+deb9u1) ...
Processing triggers for mime-support (3.60) ...
Setting up xxd (2:8.0.0197-4+deb9u1) ...
Setting up libgpm2:amd64 (1.20.4-6.2+b1) ...
Processing triggers for libc-bin (2.24-11+deb9u4) ...
Setting up vim-common (2:8.0.0197-4+deb9u1) ...
Setting up vim-runtime (2:8.0.0197-4+deb9u1) ...
Processing triggers for hicolor-icon-theme (0.15-1) ...
Setting up vim (2:8.0.0197-4+deb9u1) ...
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vim (vim) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vimdiff (vimdiff) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/rvim (rvim) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/rview (rview) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vi (vi) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/view (view) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/ex (ex) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/editor (editor) in auto mode
root@14801ba53858:/test# 
```
