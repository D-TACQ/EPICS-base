# EPICS base and support

Sample top level build for an EPICS base + asyn, StreamDevice project

**NB: hard coded path**: /home/pgm/PROJECTS .. search everything and replace with your own.. 

Do this BEFORE any build..

```bash
find . -type f -print | xargs grep /home/pgm/PROJECTS
```

## Following this install guide .. 
https://docs.epics-controls.org/projects/how-tos/en/latest/getting-started/installation.html

```bash
git clone --recursive https://github.com/epics-base/epics-base.git
cd epics-base
make

mkdir support

git clone github.com:D-TACQ/EPICS-seq.git seq

(cd seq; make)

git clone github.com:D-TACQ/asyn.git
(cd asyn; git checkout -n ACQ164 origin/ACQ164; make)

ln -s StreamDevice stream

git clone https://github.com/epics-modules/asyn.git

sudo dnf install rpcgen
sudo dnf install libtirpc-devel

git clone https://github.com/ISISComputingGroup/EPICS-pcre.git
ln -s EPICS-pcre/8-32 pcre
cd ..
source ./setup.env 
(cd support/pcre/; make)
```

 Good Job Freddie! Thanks!





