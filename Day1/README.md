# Day 1 - Docker

## ⛹️‍♂️ Lab - Installing Docker

For detailed instructions, please refer https://docs.docker.com/engine/install/centos/

```
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

Expected output
<pre>
[jegan@tektutor ~]$ docker --version
bash: docker: command not found...
[jegan@tektutor ~]$ sudo yum install -y yum-utils
[sudo] password for jegan: 
Loaded plugins: fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: mirrors.nxtgen.com
 * extras: mirrors.nxtgen.com
 * updates: mirrors.nxtgen.com
Package yum-utils-1.1.31-54.el7_8.noarch already installed and latest version
Nothing to do
[jegan@tektutor ~]$ sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
Loaded plugins: fastestmirror, langpacks
adding repo from: https://download.docker.com/linux/centos/docker-ce.repo
grabbing file https://download.docker.com/linux/centos/docker-ce.repo to /etc/yum.repos.d/docker-ce.repo
repo saved to /etc/yum.repos.d/docker-ce.repo
[jegan@tektutor ~]$ sudo yum install docker-ce docker-ce-cli containerd.io docker-compose-plugin
Loaded plugins: fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: mirrors.nxtgen.com
 * extras: mirrors.nxtgen.com
 * updates: mirrors.nxtgen.com
docker-ce-stable                                                              | 3.5 kB  00:00:00     
(1/2): docker-ce-stable/7/x86_64/updateinfo                                   |   55 B  00:00:00     
(2/2): docker-ce-stable/7/x86_64/primary_db                                   |  80 kB  00:00:00     
Resolving Dependencies
--> Running transaction check
---> Package containerd.io.x86_64 0:1.6.7-3.1.el7 will be installed
--> Processing Dependency: container-selinux >= 2:2.74 for package: containerd.io-1.6.7-3.1.el7.x86_64
---> Package docker-ce.x86_64 3:20.10.17-3.el7 will be installed
--> Processing Dependency: docker-ce-rootless-extras for package: 3:docker-ce-20.10.17-3.el7.x86_64
---> Package docker-ce-cli.x86_64 1:20.10.17-3.el7 will be installed
--> Processing Dependency: docker-scan-plugin(x86-64) for package: 1:docker-ce-cli-20.10.17-3.el7.x86_64
---> Package docker-compose-plugin.x86_64 0:2.6.0-3.el7 will be installed
--> Running transaction check
---> Package container-selinux.noarch 2:2.119.2-1.911c772.el7_8 will be installed
---> Package docker-ce-rootless-extras.x86_64 0:20.10.17-3.el7 will be installed
--> Processing Dependency: fuse-overlayfs >= 0.7 for package: docker-ce-rootless-extras-20.10.17-3.el7.x86_64
--> Processing Dependency: slirp4netns >= 0.4 for package: docker-ce-rootless-extras-20.10.17-3.el7.x86_64
---> Package docker-scan-plugin.x86_64 0:0.17.0-3.el7 will be installed
--> Running transaction check
---> Package fuse-overlayfs.x86_64 0:0.7.2-6.el7_8 will be installed
--> Processing Dependency: libfuse3.so.3(FUSE_3.2)(64bit) for package: fuse-overlayfs-0.7.2-6.el7_8.x86_64
--> Processing Dependency: libfuse3.so.3(FUSE_3.0)(64bit) for package: fuse-overlayfs-0.7.2-6.el7_8.x86_64
--> Processing Dependency: libfuse3.so.3()(64bit) for package: fuse-overlayfs-0.7.2-6.el7_8.x86_64
---> Package slirp4netns.x86_64 0:0.4.3-4.el7_8 will be installed
--> Running transaction check
---> Package fuse3-libs.x86_64 0:3.6.1-4.el7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

=====================================================================================================
 Package                       Arch       Version                         Repository            Size
=====================================================================================================
Installing:
 containerd.io                 x86_64     1.6.7-3.1.el7                   docker-ce-stable      33 M
 docker-ce                     x86_64     3:20.10.17-3.el7                docker-ce-stable      22 M
 docker-ce-cli                 x86_64     1:20.10.17-3.el7                docker-ce-stable      29 M
 docker-compose-plugin         x86_64     2.6.0-3.el7                     docker-ce-stable     7.0 M
Installing for dependencies:
 container-selinux             noarch     2:2.119.2-1.911c772.el7_8       extras                40 k
 docker-ce-rootless-extras     x86_64     20.10.17-3.el7                  docker-ce-stable     8.2 M
 docker-scan-plugin            x86_64     0.17.0-3.el7                    docker-ce-stable     3.7 M
 fuse-overlayfs                x86_64     0.7.2-6.el7_8                   extras                54 k
 fuse3-libs                    x86_64     3.6.1-4.el7                     extras                82 k
 slirp4netns                   x86_64     0.4.3-4.el7_8                   extras                81 k

Transaction Summary
=====================================================================================================
Install  4 Packages (+6 Dependent packages)

Total download size: 104 M
Installed size: 419 M
Is this ok [y/d/N]: y
Downloading packages:
warning: /var/cache/yum/x86_64/7/extras/packages/container-selinux-2.119.2-1.911c772.el7_8.noarch.rpm: Header V3 RSA/SHA256 Signature, key ID f4a80eb5: NOKEY
Public key for container-selinux-2.119.2-1.911c772.el7_8.noarch.rpm is not installed
(1/10): container-selinux-2.119.2-1.911c772.el7_8.noarch.rpm                  |  40 kB  00:00:00     
warning: /var/cache/yum/x86_64/7/docker-ce-stable/packages/docker-ce-20.10.17-3.el7.x86_64.rpm: Header V4 RSA/SHA512 Signature, key ID 621e9f35: NOKEY
Public key for docker-ce-20.10.17-3.el7.x86_64.rpm is not installed
(2/10): docker-ce-20.10.17-3.el7.x86_64.rpm                                                       |  22 MB  00:00:04     
(3/10): docker-ce-cli-20.10.17-3.el7.x86_64.rpm                                                   |  29 MB  00:00:04     
(4/10): docker-ce-rootless-extras-20.10.17-3.el7.x86_64.rpm                                       | 8.2 MB  00:00:01     
(5/10): containerd.io-1.6.7-3.1.el7.x86_64.rpm                                                    |  33 MB  00:00:11     
(6/10): fuse-overlayfs-0.7.2-6.el7_8.x86_64.rpm                                                   |  54 kB  00:00:00     
(7/10): slirp4netns-0.4.3-4.el7_8.x86_64.rpm                                                      |  81 kB  00:00:00     
(8/10): docker-compose-plugin-2.6.0-3.el7.x86_64.rpm                                              | 7.0 MB  00:00:01     
(9/10): fuse3-libs-3.6.1-4.el7.x86_64.rpm                                                         |  82 kB  00:00:00     
(10/10): docker-scan-plugin-0.17.0-3.el7.x86_64.rpm                                               | 3.7 MB  00:00:00     
-------------------------------------------------------------------------------------------------------------------------
Total                                                                                    8.5 MB/s | 104 MB  00:00:12     
Retrieving key from file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
Importing GPG key 0xF4A80EB5:
 Userid     : "CentOS-7 Key (CentOS 7 Official Signing Key) <security@centos.org>"
 Fingerprint: 6341 ab27 53d7 8a78 a7c2 7bb1 24c6 a8a7 f4a8 0eb5
 Package    : centos-release-7-9.2009.0.el7.centos.x86_64 (@anaconda)
 From       : /etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
Is this ok [y/N]: y
Retrieving key from https://download.docker.com/linux/centos/gpg
Importing GPG key 0x621E9F35:
 Userid     : "Docker Release (CE rpm) <docker@docker.com>"
 Fingerprint: 060a 61c5 1b55 8a7f 742b 77aa c52f eb6b 621e 9f35
 From       : https://download.docker.com/linux/centos/gpg
Is this ok [y/N]: y
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : docker-scan-plugin-0.17.0-3.el7.x86_64                                                               1/10 
  Installing : 1:docker-ce-cli-20.10.17-3.el7.x86_64                                                                2/10 
  Installing : 2:container-selinux-2.119.2-1.911c772.el7_8.noarch                                                   3/10 
  Installing : containerd.io-1.6.7-3.1.el7.x86_64                                                                                      4/10 
  Installing : slirp4netns-0.4.3-4.el7_8.x86_64                                                                                        5/10 
  Installing : fuse3-libs-3.6.1-4.el7.x86_64                                                                                           6/10 
  Installing : fuse-overlayfs-0.7.2-6.el7_8.x86_64                                                                                     7/10 
  Installing : 3:docker-ce-20.10.17-3.el7.x86_64                                                                                       8/10 
  Installing : docker-ce-rootless-extras-20.10.17-3.el7.x86_64                                                                         9/10 
  Installing : docker-compose-plugin-2.6.0-3.el7.x86_64                                                                               10/10 
  Verifying  : fuse3-libs-3.6.1-4.el7.x86_64                                                                                           1/10 
  Verifying  : docker-ce-rootless-extras-20.10.17-3.el7.x86_64                                                                         2/10 
  Verifying  : 1:docker-ce-cli-20.10.17-3.el7.x86_64                                                                                   3/10 
  Verifying  : containerd.io-1.6.7-3.1.el7.x86_64                                                                                      4/10 
  Verifying  : slirp4netns-0.4.3-4.el7_8.x86_64                                                                                        5/10 
  Verifying  : 2:container-selinux-2.119.2-1.911c772.el7_8.noarch                                                                      6/10 
  Verifying  : 3:docker-ce-20.10.17-3.el7.x86_64                                                                                       7/10 
  Verifying  : docker-scan-plugin-0.17.0-3.el7.x86_64                                                                                  8/10 
  Verifying  : fuse-overlayfs-0.7.2-6.el7_8.x86_64                                                                                     9/10 
  Verifying  : docker-compose-plugin-2.6.0-3.el7.x86_64                                                                               10/10 

Installed:
  containerd.io.x86_64 0:1.6.7-3.1.el7               docker-ce.x86_64 3:20.10.17-3.el7         docker-ce-cli.x86_64 1:20.10.17-3.el7        
  docker-compose-plugin.x86_64 0:2.6.0-3.el7        

Dependency Installed:
  container-selinux.noarch 2:2.119.2-1.911c772.el7_8                    docker-ce-rootless-extras.x86_64 0:20.10.17-3.el7                   
  docker-scan-plugin.x86_64 0:0.17.0-3.el7                              fuse-overlayfs.x86_64 0:0.7.2-6.el7_8                               
  fuse3-libs.x86_64 0:3.6.1-4.el7                                       slirp4netns.x86_64 0:0.4.3-4.el7_8                                  

Complete!
</pre>


## ⛹️‍♂️ Lab -  Checking docker version
```
docker --version
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker --version</b>
Docker version 20.10.17, build 100c701
</pre>

## ⛹️‍♂️ Lab -  Issuing docker commands
```
docker images
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker images</b>
Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?
</pre>

## ⛹️‍♂️ Lab -  Starting the Docker server daemon
```
sudo systemctl enable docker
sudo systemctl start docker
sudo systemctl status docker
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>sudo systemctl enable docker</b>
[sudo] password for jegan: 
Created symlink from /etc/systemd/system/multi-user.target.wants/docker.service to /usr/lib/systemd/system/docker.service.
[jegan@tektutor ~]$ <b>sudo systemctl start docker</b>
[jegan@tektutor ~]$ <b>sudo systemctl status docker</b>
● docker.service - Docker Application Container Engine
   Loaded: loaded (/usr/lib/systemd/system/docker.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2022-08-22 02:02:45 PDT; 3s ago
     Docs: https://docs.docker.com
 Main PID: 61106 (dockerd)
    Tasks: 9
   Memory: 36.3M
   CGroup: /system.slice/docker.service
           └─61106 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock

Aug 22 02:02:44 tektutor.org dockerd[61106]: time="2022-08-22T02:02:44.085019342-07:00" level=info msg="ccResolve...=grpc
Aug 22 02:02:44 tektutor.org dockerd[61106]: time="2022-08-22T02:02:44.085119207-07:00" level=info msg="ClientCon...=grpc
Aug 22 02:02:44 tektutor.org dockerd[61106]: time="2022-08-22T02:02:44.118194019-07:00" level=info msg="Loading c...art."
Aug 22 02:02:45 tektutor.org dockerd[61106]: time="2022-08-22T02:02:45.440720656-07:00" level=info msg="Default b...ress"
Aug 22 02:02:45 tektutor.org dockerd[61106]: time="2022-08-22T02:02:45.646307670-07:00" level=info msg="Firewalld...ning"
Aug 22 02:02:45 tektutor.org dockerd[61106]: time="2022-08-22T02:02:45.884085080-07:00" level=info msg="Loading c...one."
Aug 22 02:02:45 tektutor.org dockerd[61106]: time="2022-08-22T02:02:45.929330766-07:00" level=info msg="Docker da...10.17
Aug 22 02:02:45 tektutor.org dockerd[61106]: time="2022-08-22T02:02:45.929715135-07:00" level=info msg="Daemon ha...tion"
Aug 22 02:02:45 tektutor.org systemd[1]: Started Docker Application Container Engine.
Aug 22 02:02:45 tektutor.org dockerd[61106]: time="2022-08-22T02:02:45.989156586-07:00" level=info msg="API liste...sock"
Hint: Some lines were ellipsized, use -l to show in full.
</pre>

## ⛹️‍♂️ Lab -  Try listing images
```
docker images
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker images</b>
Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/images/json": dial unix /var/run/docker.sock: connect: permission denied
</pre>

## ⛹️‍♂️ Lab -  Troubleshooting Docker permission denied error
```
docker images
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker images</b>
Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/images/json": dial unix /var/run/docker.sock: connect: permission denied
[jegan@tektutor ~]$ <b>id</b>
uid=1000(jegan) gid=1000(jegan) groups=1000(jegan) context=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023
[jegan@tektutor ~]$ <b>sudo usermod -aG docker jegan</b>
[sudo] password for jegan: 
[jegan@tektutor ~]$ <b>id</b>
uid=1000(jegan) gid=1000(jegan) groups=1000(jegan) context=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023
[jegan@tektutor ~]$ <b>newgrp docker</b>
[jegan@tektutor ~]$ <b>id</b>
uid=1000(jegan) gid=981(docker) groups=981(docker),1000(jegan) context=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023
[jegan@tektutor ~]$ <b>docker images</b>
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE
</pre>


# Docker Commands

## ⛹️‍♂️ Lab -  Finding details about your docker installation
```
docker info
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker info</b>
Client:
 Context:    default
 Debug Mode: false
 Plugins:
  app: Docker App (Docker Inc., v0.9.1-beta3)
  buildx: Docker Buildx (Docker Inc., v0.8.2-docker)
  compose: Docker Compose (Docker Inc., v2.6.0)
  scan: Docker Scan (Docker Inc., v0.17.0)

Server:
 Containers: 0
  Running: 0
  Paused: 0
  Stopped: 0
 Images: 0
 Server Version: 20.10.17
 Storage Driver: overlay2
  Backing Filesystem: xfs
  Supports d_type: true
  Native Overlay Diff: true
  userxattr: false
 Logging Driver: json-file
 Cgroup Driver: cgroupfs
 Cgroup Version: 1
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local logentries splunk syslog
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 io.containerd.runtime.v1.linux runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: 0197261a30bf81f1ee8e6a4dd2dea0ef95d67ccb
 runc version: v1.1.3-0-g6724737
 init version: de40ad0
 Security Options:
  seccomp
   Profile: default
 Kernel Version: 3.10.0-1160.el7.x86_64
 Operating System: CentOS Linux 7 (Core)
 OSType: linux
 Architecture: x86_64
 CPUs: 4
 Total Memory: 15.49GiB
 Name: tektutor.org
 ID: E5JH:7QFK:RR5Q:MWAX:A7DA:PJGE:W6IV:A6K5:W3P5:GFBA:2MK7:EMMM
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 Registry: https://index.docker.io/v1/
 Labels:
 Experimental: false
 Insecure Registries:
  127.0.0.0/8
 Live Restore Enabled: false
</pre>

## ⛹️‍♂️ Lab -  Listing docker images from your local docker registry
```
docker images
```
Expected output
<pre>
jegan@tektutor ~]$ <b>docker images</b>
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE
[jegan@tektutor ~]$ <b>docker pull hello-world:latest</b>
latest: Pulling from library/hello-world
2db29710123e: Pull complete 
Digest: sha256:7d246653d0511db2a6b2e0436cfd0e52ac8c066000264b3ce63331ac66dca625
Status: Downloaded newer image for hello-world:latest
docker.io/library/hello-world:latest
[jegan@tektutor ~]$ <b>docker images</b>
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
hello-world   latest    feb5d9fea6a5   11 months ago   13.3kB
</pre>


## ⛹️‍♂️ Lab -  Downloading docker image from Docker Hub to Local registry
```
docker pull hello-world:latest
```

## ⛹️‍♂️ Lab -  Downloading mysql container image
```
docker pull mysql:5.7
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker pull mysql:5.7</b>
5.7: Pulling from library/mysql
66fb34780033: Pull complete 
ef4ccd63cdb4: Pull complete 
d6f28a94c51f: Pull complete 
7feea2a503b5: Pull complete 
71dd5852ecd9: Pull complete 
2ff5c3b24fd5: Pull complete 
88a546386a61: Pull complete 
65b18297cf83: Pull complete 
d64f23335fb8: Pull complete 
6ba4171261fa: Pull complete 
96dcc6c8de93: Pull complete 
Digest: sha256:b3a86578a582617214477d91e47e850f9e18df0b5d1644fb2d96d91a340b8972
Status: Downloaded newer image for mysql:5.7
docker.io/library/mysql:5.7
[jegan@tektutor ~]$ <b>docker images</b>
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
mysql         5.7       3147495b3a5c   3 weeks ago     431MB
hello-world   latest    feb5d9fea6a5   11 months ago   13.3kB
</pre>

## ⛹️‍♂️ Lab -  Finding hello-world docker image details and its layers
```
docker image inspect hello-world:latest
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker image inspect hello-world:latest</b>
[
    {
        "Id": "sha256:feb5d9fea6a5e9606aa995e879d862b825965ba48de054caab5ef356dc6b3412",
        "RepoTags": [
            "hello-world:latest"
        ],
        "RepoDigests": [
            "hello-world@sha256:7d246653d0511db2a6b2e0436cfd0e52ac8c066000264b3ce63331ac66dca625"
        ],
        "Parent": "",
        "Comment": "",
        "Created": "2021-09-23T23:47:57.442225064Z",
        "Container": "8746661ca3c2f215da94e6d3f7dfdcafaff5ec0b21c9aff6af3dc379a82fbc72",
        "ContainerConfig": {
            "Hostname": "8746661ca3c2",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
            ],
            "Cmd": [
                "/bin/sh",
                "-c",
                "#(nop) ",
                "CMD [\"/hello\"]"
            ],
            "Image": "sha256:b9935d4e8431fb1a7f0989304ec86b3329a99a25f5efdc7f09f3f8c41434ca6d",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": null,
            "OnBuild": null,
            "Labels": {}
        },
        "DockerVersion": "20.10.7",
        "Author": "",
        "Config": {
            "Hostname": "",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
            ],
            "Cmd": [
                "/hello"
            ],
            "Image": "sha256:b9935d4e8431fb1a7f0989304ec86b3329a99a25f5efdc7f09f3f8c41434ca6d",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": null,
            "OnBuild": null,
            "Labels": null
        },
        "Architecture": "amd64",
        "Os": "linux",
        "Size": 13256,
        "VirtualSize": 13256,
        "GraphDriver": {
            "Data": {
                "MergedDir": "/var/lib/docker/overlay2/5a2e3911b8d8cc55fb5425af3d58ed4a8e6d14cdb63e3fbde35afbcb2acc6a6f/merged",
                "UpperDir": "/var/lib/docker/overlay2/5a2e3911b8d8cc55fb5425af3d58ed4a8e6d14cdb63e3fbde35afbcb2acc6a6f/diff",
                "WorkDir": "/var/lib/docker/overlay2/5a2e3911b8d8cc55fb5425af3d58ed4a8e6d14cdb63e3fbde35afbcb2acc6a6f/work"
            },
            "Name": "overlay2"
        },
        "RootFS": {
            "Type": "layers",
            "Layers": [
                "sha256:e07ee1baac5fae6a26f30cabfe54a36d3402f96afda318fe0a96cec4ca393359"
            ]
        },
        "Metadata": {
            "LastTagTime": "0001-01-01T00:00:00Z"
        }
    }
]
</pre>

## ⛹️‍♂️ Lab -  Deleting an image from Local Docker Registry
```
docker rmi hello-world:latest
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker rmi hello-world:latest</b>
Untagged: hello-world:latest
Untagged: hello-world@sha256:7d246653d0511db2a6b2e0436cfd0e52ac8c066000264b3ce63331ac66dca625
Deleted: sha256:feb5d9fea6a5e9606aa995e879d862b825965ba48de054caab5ef356dc6b3412
Deleted: sha256:e07ee1baac5fae6a26f30cabfe54a36d3402f96afda318fe0a96cec4ca393359
</pre>

## ⛹️‍♂️ Lab - Creating conainer from docker image
```
docker run hello-world:latest
```

## ⛹️‍♂️ Lab - Listing running containers
```
docker ps
```

## Creating an ubuntu container in background mode
```
docker run -dit --name ubuntu1 --hostname ubuntu1 ubuntu:16.04 /bin/bash
docker images
docker ps
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker run -dit --name ubuntu1 --hostname ubuntu1 ubuntu:16.04 /bin/bash</b>
Unable to find image 'ubuntu:16.04' locally
16.04: Pulling from library/ubuntu
58690f9b18fc: Pull complete 
b51569e7c507: Pull complete 
da8ef40b9eca: Pull complete 
fb15d46c38dc: Pull complete 
Digest: sha256:91bd29a464fdabfcf44e29e1f2a5f213c6dfa750b6290e40dd6998ac79da3c41
Status: Downloaded newer image for ubuntu:16.04
a26ad7017979136a0ea0871f390c5547834a9298f91a3339bc5d71b99ccb701f
[jegan@tektutor ~]$ <b>docker images</b>
REPOSITORY   TAG       IMAGE ID       CREATED         SIZE
mysql        5.7       3147495b3a5c   3 weeks ago     431MB
<b>ubuntu       16.04     b6f507652425   11 months ago   135MB</b>
[jegan@tektutor ~]$ <b>docker ps</b>
CONTAINER ID   IMAGE          COMMAND       CREATED          STATUS          PORTS     NAMES
a26ad7017979   ubuntu:16.04   "/bin/bash"   40 seconds ago   Up 38 seconds             ubuntu1
</pre>


## ⛹️‍♂️ Lab - Finding details about a container
```
docker container inspect ubuntu1
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker container inspect ubuntu1</b>
[
    {
        "Id": "a26ad7017979136a0ea0871f390c5547834a9298f91a3339bc5d71b99ccb701f",
        "Created": "2022-08-22T11:20:00.778105243Z",
        "Path": "/bin/bash",
        "Args": [],
        "State": {
            "Status": "running",
            "Running": true,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 65372,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2022-08-22T11:20:01.456885227Z",
            "FinishedAt": "0001-01-01T00:00:00Z"
        },
        "Image": "sha256:b6f50765242581c887ff1acc2511fa2d885c52d8fb3ac8c4bba131fd86567f2e",
        "ResolvConfPath": "/var/lib/docker/containers/a26ad7017979136a0ea0871f390c5547834a9298f91a3339bc5d71b99ccb701f/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/a26ad7017979136a0ea0871f390c5547834a9298f91a3339bc5d71b99ccb701f/hostname",
        "HostsPath": "/var/lib/docker/containers/a26ad7017979136a0ea0871f390c5547834a9298f91a3339bc5d71b99ccb701f/hosts",
        "LogPath": "/var/lib/docker/containers/a26ad7017979136a0ea0871f390c5547834a9298f91a3339bc5d71b99ccb701f/a26ad7017979136a0ea0871f390c5547834a9298f91a3339bc5d71b99ccb701f-json.log",
        "Name": "/ubuntu1",
        "RestartCount": 0,
        "Driver": "overlay2",
        "Platform": "linux",
        "MountLabel": "",
        "ProcessLabel": "",
        "AppArmorProfile": "",
        "ExecIDs": null,
        "HostConfig": {
            "Binds": null,
            "ContainerIDFile": "",
            "LogConfig": {
                "Type": "json-file",
                "Config": {}
            },
            "NetworkMode": "default",
            "PortBindings": {},
            "RestartPolicy": {
                "Name": "no",
                "MaximumRetryCount": 0
            },
            "AutoRemove": false,
            "VolumeDriver": "",
            "VolumesFrom": null,
            "CapAdd": null,
            "CapDrop": null,
            "CgroupnsMode": "host",
            "Dns": [],
            "DnsOptions": [],
            "DnsSearch": [],
            "ExtraHosts": null,
            "GroupAdd": null,
            "IpcMode": "private",
            "Cgroup": "",
            "Links": null,
            "OomScoreAdj": 0,
            "PidMode": "",
            "Privileged": false,
            "PublishAllPorts": false,
            "ReadonlyRootfs": false,
            "SecurityOpt": null,
            "UTSMode": "",
            "UsernsMode": "",
            "ShmSize": 67108864,
            "Runtime": "runc",
            "ConsoleSize": [
                0,
                0
            ],
            "Isolation": "",
            "CpuShares": 0,
            "Memory": 0,
            "NanoCpus": 0,
            "CgroupParent": "",
            "BlkioWeight": 0,
            "BlkioWeightDevice": [],
            "BlkioDeviceReadBps": null,
            "BlkioDeviceWriteBps": null,
            "BlkioDeviceReadIOps": null,
            "BlkioDeviceWriteIOps": null,
            "CpuPeriod": 0,
            "CpuQuota": 0,
            "CpuRealtimePeriod": 0,
            "CpuRealtimeRuntime": 0,
            "CpusetCpus": "",
            "CpusetMems": "",
            "Devices": [],
            "DeviceCgroupRules": null,
            "DeviceRequests": null,
            "KernelMemory": 0,
            "KernelMemoryTCP": 0,
            "MemoryReservation": 0,
            "MemorySwap": 0,
            "MemorySwappiness": null,
            "OomKillDisable": false,
            "PidsLimit": null,
            "Ulimits": null,
            "CpuCount": 0,
            "CpuPercent": 0,
            "IOMaximumIOps": 0,
            "IOMaximumBandwidth": 0,
            "MaskedPaths": [
                "/proc/asound",
                "/proc/acpi",
                "/proc/kcore",
                "/proc/keys",
                "/proc/latency_stats",
                "/proc/timer_list",
                "/proc/timer_stats",
                "/proc/sched_debug",
                "/proc/scsi",
                "/sys/firmware"
            ],
            "ReadonlyPaths": [
                "/proc/bus",
                "/proc/fs",
                "/proc/irq",
                "/proc/sys",
                "/proc/sysrq-trigger"
            ]
        },
        "GraphDriver": {
            "Data": {
                "LowerDir": "/var/lib/docker/overlay2/1a59b173e551c7a8eeea89c94027de73ef96b84658563081562a9b3aa5f2dc4f-init/diff:/var/lib/docker/overlay2/38ba3b9dcdc6e62fc41ad9d143d627e3f91c8ab1da61b20301c3ac6724344f4e/diff:/var/lib/docker/overlay2/7307a25d585ea21f6452eaa091a576d9d89a4ccdf3d4f3f320cdcabc284ee8b0/diff:/var/lib/docker/overlay2/b46e772e90769c6ba823d6022aae8f266e586aec51c4b3372296db3ebacd7222/diff:/var/lib/docker/overlay2/121e2da19bf1a58d772f590d54c21bb6d05c46aa7f78dc3b26a943bbdc9a8ac9/diff",
                "MergedDir": "/var/lib/docker/overlay2/1a59b173e551c7a8eeea89c94027de73ef96b84658563081562a9b3aa5f2dc4f/merged",
                "UpperDir": "/var/lib/docker/overlay2/1a59b173e551c7a8eeea89c94027de73ef96b84658563081562a9b3aa5f2dc4f/diff",
                "WorkDir": "/var/lib/docker/overlay2/1a59b173e551c7a8eeea89c94027de73ef96b84658563081562a9b3aa5f2dc4f/work"
            },
            "Name": "overlay2"
        },
        "Mounts": [],
        "Config": {
            "Hostname": "ubuntu1",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "Tty": true,
            "OpenStdin": true,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
            ],
            "Cmd": [
                "/bin/bash"
            ],
            "Image": "ubuntu:16.04",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": null,
            "OnBuild": null,
            "Labels": {}
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "daef6b9ac611ce50f522e545d036e667c68419224b680efb389273f5b8a17563",
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "Ports": {},
            "SandboxKey": "/var/run/docker/netns/daef6b9ac611",
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "f16e78288ebd7a430e495db07fa3dc7f3c3390444626116d503416afc25f7a86",
            "Gateway": "172.17.0.1",
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "172.17.0.2",
            "IPPrefixLen": 16,
            "IPv6Gateway": "",
            "MacAddress": "02:42:ac:11:00:02",
            "Networks": {
                "bridge": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "NetworkID": "416244ff523183a048ef390912399710b3d7b0724073dff3e1f9039b650dbf0f",
                    "EndpointID": "f16e78288ebd7a430e495db07fa3dc7f3c3390444626116d503416afc25f7a86",
                    "Gateway": "172.17.0.1",
                    "IPAddress": "172.17.0.2",
                    "IPPrefixLen": 16,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "MacAddress": "02:42:ac:11:00:02",
                    "DriverOpts": null
                }
            }
        }
    }
]
</pre>

## ⛹️‍♂️ Lab - Listing networks supported by docker
```
docker network ls
```
Expected output
<pre>
[jegan@tektutor ~]$ <b>docker network ls</b>
NETWORK ID     NAME      DRIVER    SCOPE
416244ff5231   bridge    bridge    local
ab0f9d816329   host      host      local
3cc6698f929e   none      null      local
</pre>

## ⛹️‍♂️ Lab - Inspecting docker bridge network
```
docker network inspect bridge
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker network inspect bridge</b>
[
    {
        "Name": "bridge",
        "Id": "416244ff523183a048ef390912399710b3d7b0724073dff3e1f9039b650dbf0f",
        "Created": "2022-08-22T02:02:45.440808978-07:00",
        "Scope": "local",
        "Driver": "bridge",
        "EnableIPv6": false,
        "IPAM": {
            "Driver": "default",
            "Options": null,
            "Config": [
                {
                    "Subnet": "172.17.0.0/16"
                }
            ]
        },
        "Internal": false,
        "Attachable": false,
        "Ingress": false,
        "ConfigFrom": {
            "Network": ""
        },
        "ConfigOnly": false,
        "Containers": {
            "a26ad7017979136a0ea0871f390c5547834a9298f91a3339bc5d71b99ccb701f": {
                "Name": "ubuntu1",
                "EndpointID": "f16e78288ebd7a430e495db07fa3dc7f3c3390444626116d503416afc25f7a86",
                "MacAddress": "02:42:ac:11:00:02",
                "IPv4Address": "172.17.0.2/16",
                "IPv6Address": ""
            }
        },
        "Options": {
            "com.docker.network.bridge.default_bridge": "true",
            "com.docker.network.bridge.enable_icc": "true",
            "com.docker.network.bridge.enable_ip_masquerade": "true",
            "com.docker.network.bridge.host_binding_ipv4": "0.0.0.0",
            "com.docker.network.bridge.name": "docker0",
            "com.docker.network.driver.mtu": "1500"
        },
        "Labels": {}
    }
]
</pre>


## ⛹️‍♂️ Lab - Creating a custom network with a custom subnet address
```
docker network create my-network-1 --subnet=192.200.255.0/24
docker network ls
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker network create my-network-1 --subnet=192.200.255.0/24</b>
566b5aa8d9039ff5a802dcd74e78c24ab84f11b8c4aaaa95458384a30fdf6934
[jegan@tektutor ~]$ <b>docker network ls</b>
NETWORK ID     NAME           DRIVER    SCOPE
416244ff5231   bridge         bridge    local
ab0f9d816329   host           host      local
566b5aa8d903   my-network-1   bridge    local
3cc6698f929e   none           null      local
</pre>

## ⛹️‍♂️ Lab - Inspecting our custom network to find more details
```
docker network inspect my-network-1
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker network ls</b>
NETWORK ID     NAME           DRIVER    SCOPE
416244ff5231   bridge         bridge    local
ab0f9d816329   host           host      local
566b5aa8d903   my-network-1   bridge    local
3cc6698f929e   none           null      local
[jegan@tektutor ~]$ <b>docker network inspect my-network-1</b>
[
    {
        "Name": "my-network-1",
        "Id": "566b5aa8d9039ff5a802dcd74e78c24ab84f11b8c4aaaa95458384a30fdf6934",
        "Created": "2022-08-22T04:36:23.878896167-07:00",
        "Scope": "local",
        "Driver": "bridge",
        "EnableIPv6": false,
        "IPAM": {
            "Driver": "default",
            "Options": {},
            "Config": [
                {
                    "Subnet": "192.200.255.0/24"
                }
            ]
        },
        "Internal": false,
        "Attachable": false,
        "Ingress": false,
        "ConfigFrom": {
            "Network": ""
        },
        "ConfigOnly": false,
        "Containers": {},
        "Options": {},
        "Labels": {}
    }
]
</pre>

## ⛹️‍♂️ Lab - Creating a container and attaching that container to our custom network, finding its IP Address
```
docker run -dit --name ubuntu2 --hostname ubuntu2 --network=my-network-1 ubuntu:16.04 /bin/bash
docker inspect ubuntu2 | grep IPA
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker run -dit --name ubuntu2 --hostname ubuntu2 --network=my-network-1 ubuntu:16.04 /bin/bash</b>
33474534ad7c32796b157458be51d9479339c2fd24a895f20d1425350d4ce2a8
[jegan@tektutor ~]$ <b>docker inspect ubuntu2 | grep IPA</b>
            "SecondaryIPAddresses": null,
            "IPAddress": "",
                    "IPAMConfig": null,
                    "IPAddress": "192.200.255.2",
</pre>


## ⛹️‍♂️ Lab - Getting inside a container that runs in background
```
docker exec -it ubuntu1 bash
hostname
hostname -i
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker exec -it ubuntu1 bash</b>
root@ubuntu1:/# <b>ls</b>
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@ubuntu1:/# <b>hostname</b>
ubuntu1
root@ubuntu1:/# <b>hostname -i</b>
172.17.0.2
</pre>

## ⛹️‍♂️ Lab - Installing softwares inside a container just like we install softwares in an Ubuntu VM/OS

In the command below, ubuntu1 is the container name.
```
docker exec -it ubuntu1 /bin/bash
apt update
apt install -y net-tools iputils-ping
```

Expected output
<pre>
[jegan@tektutor ~]$ <b>docker exec -it ubuntu1 bash</b>
root@ubuntu1:/# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@ubuntu1:/# <b>hostname</b>
ubuntu1
root@ubuntu1:/# <b>hostname -i</b>
172.17.0.2
root@ubuntu1:/# <b>ifconfig</b>
bash: ifconfig: command not found
root@ubuntu1:/# <b>ip addr show</b>
bash: ip: command not found
root@ubuntu1:/# <b>ping</b>
bash: ping: command not found
root@ubuntu1:/# <b>apt update</b>
Get:1 http://archive.ubuntu.com/ubuntu xenial InRelease [247 kB]
Get:2 http://security.ubuntu.com/ubuntu xenial-security InRelease [99.8 kB]
Get:3 http://security.ubuntu.com/ubuntu xenial-security/main amd64 Packages [2051 kB]
Get:4 http://archive.ubuntu.com/ubuntu xenial-updates InRelease [99.8 kB]
Get:5 http://archive.ubuntu.com/ubuntu xenial-backports InRelease [97.4 kB]        
Get:6 http://archive.ubuntu.com/ubuntu xenial/main amd64 Packages [1558 kB]        
Get:7 http://archive.ubuntu.com/ubuntu xenial/restricted amd64 Packages [14.1 kB]           
Get:8 http://archive.ubuntu.com/ubuntu xenial/universe amd64 Packages [9827 kB]  
Get:9 http://security.ubuntu.com/ubuntu xenial-security/restricted amd64 Packages [15.9 kB]
Get:10 http://security.ubuntu.com/ubuntu xenial-security/universe amd64 Packages [984 kB]   
Get:11 http://security.ubuntu.com/ubuntu xenial-security/multiverse amd64 Packages [8820 B]
Get:12 http://archive.ubuntu.com/ubuntu xenial/multiverse amd64 Packages [176 kB]
Get:13 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 Packages [2560 kB]
Get:14 http://archive.ubuntu.com/ubuntu xenial-updates/restricted amd64 Packages [16.4 kB]
Get:15 http://archive.ubuntu.com/ubuntu xenial-updates/universe amd64 Packages [1544 kB]
Get:16 http://archive.ubuntu.com/ubuntu xenial-updates/multiverse amd64 Packages [26.2 kB]
Get:17 http://archive.ubuntu.com/ubuntu xenial-backports/main amd64 Packages [10.9 kB]
Get:18 http://archive.ubuntu.com/ubuntu xenial-backports/universe amd64 Packages [12.7 kB]
Fetched 19.3 MB in 5s (3528 kB/s)                            
Reading package lists... Done
Building dependency tree       
Reading state information... Done
All packages are up to date.
root@ubuntu1:/# <b>apt install -y net-tools iputils-ping</b>
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following additional packages will be installed:
  libffi6 libgmp10 libgnutls-openssl27 libgnutls30 libhogweed4 libidn11 libnettle6 libp11-kit0 libtasn1-6
Suggested packages:
  gnutls-bin
The following NEW packages will be installed:
  iputils-ping libffi6 libgmp10 libgnutls-openssl27 libgnutls30 libhogweed4 libidn11 libnettle6 libp11-kit0 libtasn1-6
  net-tools
0 upgraded, 11 newly installed, 0 to remove and 0 not upgraded.
Need to get 1482 kB of archives.
After this operation, 4510 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu xenial/main amd64 libgmp10 amd64 2:6.1.0+dfsg-2 [240 kB]
Get:2 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libnettle6 amd64 3.2-1ubuntu0.16.04.2 [93.7 kB]
Get:3 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libhogweed4 amd64 3.2-1ubuntu0.16.04.2 [136 kB]
Get:4 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libidn11 amd64 1.32-3ubuntu1.2 [46.5 kB]
Get:5 http://archive.ubuntu.com/ubuntu xenial/main amd64 libffi6 amd64 3.2.1-4 [17.8 kB]
Get:6 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libp11-kit0 amd64 0.23.2-5~ubuntu16.04.2 [107 kB]
Get:7 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libtasn1-6 amd64 4.7-3ubuntu0.16.04.3 [43.5 kB]
Get:8 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libgnutls30 amd64 3.4.10-4ubuntu1.9 [548 kB]
Get:9 http://archive.ubuntu.com/ubuntu xenial-updates/main amd64 libgnutls-openssl27 amd64 3.4.10-4ubuntu1.9 [21.9 kB]
Get:10 http://archive.ubuntu.com/ubuntu xenial/main amd64 iputils-ping amd64 3:20121221-5ubuntu2 [52.7 kB]
Get:11 http://archive.ubuntu.com/ubuntu xenial/main amd64 net-tools amd64 1.60-26ubuntu1 [175 kB]
Fetched 1482 kB in 1s (916 kB/s)   
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package libgmp10:amd64.
(Reading database ... 4785 files and directories currently installed.)
Preparing to unpack .../libgmp10_2%3a6.1.0+dfsg-2_amd64.deb ...
Unpacking libgmp10:amd64 (2:6.1.0+dfsg-2) ...
Selecting previously unselected package libnettle6:amd64.
Preparing to unpack .../libnettle6_3.2-1ubuntu0.16.04.2_amd64.deb ...
Unpacking libnettle6:amd64 (3.2-1ubuntu0.16.04.2) ...
Selecting previously unselected package libhogweed4:amd64.
Preparing to unpack .../libhogweed4_3.2-1ubuntu0.16.04.2_amd64.deb ...
Unpacking libhogweed4:amd64 (3.2-1ubuntu0.16.04.2) ...
Selecting previously unselected package libidn11:amd64.
Preparing to unpack .../libidn11_1.32-3ubuntu1.2_amd64.deb ...
Unpacking libidn11:amd64 (1.32-3ubuntu1.2) ...
Selecting previously unselected package libffi6:amd64.
Preparing to unpack .../libffi6_3.2.1-4_amd64.deb ...
Unpacking libffi6:amd64 (3.2.1-4) ...
Selecting previously unselected package libp11-kit0:amd64.
Preparing to unpack .../libp11-kit0_0.23.2-5~ubuntu16.04.2_amd64.deb ...
Unpacking libp11-kit0:amd64 (0.23.2-5~ubuntu16.04.2) ...
Selecting previously unselected package libtasn1-6:amd64.
Preparing to unpack .../libtasn1-6_4.7-3ubuntu0.16.04.3_amd64.deb ...
Unpacking libtasn1-6:amd64 (4.7-3ubuntu0.16.04.3) ...
Selecting previously unselected package libgnutls30:amd64.
Preparing to unpack .../libgnutls30_3.4.10-4ubuntu1.9_amd64.deb ...
Unpacking libgnutls30:amd64 (3.4.10-4ubuntu1.9) ...
Selecting previously unselected package libgnutls-openssl27:amd64.
Preparing to unpack .../libgnutls-openssl27_3.4.10-4ubuntu1.9_amd64.deb ...
Unpacking libgnutls-openssl27:amd64 (3.4.10-4ubuntu1.9) ...
Selecting previously unselected package iputils-ping.
Preparing to unpack .../iputils-ping_3%3a20121221-5ubuntu2_amd64.deb ...
Unpacking iputils-ping (3:20121221-5ubuntu2) ...
Selecting previously unselected package net-tools.
Preparing to unpack .../net-tools_1.60-26ubuntu1_amd64.deb ...
Unpacking net-tools (1.60-26ubuntu1) ...
Processing triggers for libc-bin (2.23-0ubuntu11.3) ...
Setting up libgmp10:amd64 (2:6.1.0+dfsg-2) ...
Setting up libnettle6:amd64 (3.2-1ubuntu0.16.04.2) ...
Setting up libhogweed4:amd64 (3.2-1ubuntu0.16.04.2) ...
Setting up libidn11:amd64 (1.32-3ubuntu1.2) ...
Setting up libffi6:amd64 (3.2.1-4) ...
Setting up libp11-kit0:amd64 (0.23.2-5~ubuntu16.04.2) ...
Setting up libtasn1-6:amd64 (4.7-3ubuntu0.16.04.3) ...
Setting up libgnutls30:amd64 (3.4.10-4ubuntu1.9) ...
Setting up libgnutls-openssl27:amd64 (3.4.10-4ubuntu1.9) ...
Setting up iputils-ping (3:20121221-5ubuntu2) ...
Setcap is not installed, falling back to setuid
Setting up net-tools (1.60-26ubuntu1) ...
Processing triggers for libc-bin (2.23-0ubuntu11.3) ...
root@ubuntu1:/# <b>ifconfig</b>
eth0      Link encap:Ethernet  HWaddr 02:42:ac:11:00:02  
          inet addr:172.17.0.2  Bcast:172.17.255.255  Mask:255.255.0.0
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:3596 errors:0 dropped:0 overruns:0 frame:0
          TX packets:2867 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0 
          RX bytes:21034522 (21.0 MB)  TX bytes:160830 (160.8 KB)

lo        Link encap:Local Loopback  
          inet addr:127.0.0.1  Mask:255.0.0.0
          UP LOOPBACK RUNNING  MTU:65536  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:0 (0.0 B)  TX bytes:0 (0.0 B)

root@ubuntu1:/# <b>ping 192.168.1.80</b>
PING 192.168.1.80 (192.168.1.80) 56(84) bytes of data.
64 bytes from 192.168.1.80: icmp_seq=1 ttl=127 time=0.550 ms
64 bytes from 192.168.1.80: icmp_seq=2 ttl=127 time=0.589 ms
64 bytes from 192.168.1.80: icmp_seq=3 ttl=127 time=0.526 ms
64 bytes from 192.168.1.80: icmp_seq=4 ttl=127 time=0.476 ms
64 bytes from 192.168.1.80: icmp_seq=5 ttl=127 time=0.581 ms
64 bytes from 192.168.1.80: icmp_seq=6 ttl=127 time=0.599 ms
^C
--- 192.168.1.80 ping statistics ---
6 packets transmitted, 6 received, 0% packet loss, time 5000ms
rtt min/avg/max/mdev = 0.476/0.553/0.599/0.048 ms
root@ubuntu1:/# 
</pre>
