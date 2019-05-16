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

root@14801ba53858:/test# 

```
