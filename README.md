# NVIDIA ENROOT 3.2.0 DEPENDENCIES FOR CENTOS 7 (GCC 4.8.5) #

This repository contains all the required dependencies (precompiled) for [ENROOT](https://github.com/NVIDIA/enroot) to run on CentOS 7 (GCC 4.8.5)

## Dependencies : ##
  * bmake (20201212) 
  * fuse-overlayfs  
  * gperf (3.1)
  * jq  (1.6)
  * libcap  (2.46)
  * libfuse (3.10.1)
  * libfuse-fuse  (3.10.1)
  * libnvidia-container (1.3.1)
  * libseccomp  (2.5.1)
  * parallel  (20201122)
  * pigz  (2.4)
  * squashfuse 
  * terraform (0.14.3)

## Environment Setup : ##
```sh
  export DEPS=<path to the directory where repository is cloned>
  export PATH=$PATH:$DEPS/bin
  export INCLUDE=$INCLUDE:$DEPS/include
  export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$DEPS/lib
```

## IMPORTANT : ##
```sh
ERROR : enroot-nsenter: failed to create user namespace: Invalid argument

/proc/sys/user/max_user_namespaces must be greater than 1
/proc/sys/user/max_mnt_namespaces must be greater than 1
cat /proc/sys/user/max_user_namespaces
0
cat /proc/sys/user/max_mnt_namespaces
25543
Solution :
echo 100 > /proc/sys/user/max_user_namespaces
```
##  [CLICK HERE FOR DETAILED ENROOT INSTALLTION AND CONFIGURATION REFERENCE GUIDE](https://supercomputing.iitd.ac.in/publicpdfs/enrootpublicdoc.pdf) ## 
