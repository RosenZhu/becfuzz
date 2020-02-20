# collision free

## Install Dyninst

[the branch](https://github.com/mxz297/dyninst)

```
git clone https://github.com/mxz297/dyninst.git
cd dyninst
git checkout fuzzing
```
[install instructions](https://github.com/mxz297/dyninst)

## environment
```
export DYNINST_INSTALL=/path/to/dynBuildDir
export BECFUZZ_PATH=/path/to/becfuzz

export DYNINSTAPI_RT_LIB=$DYNINST_INSTALL/lib/libdyninstAPI_RT.so
export LD_LIBRARY_PATH=$DYNINST_INSTALL/lib:$BECFUZZ_PATH
export PATH=$PATH:$BECFUZZ_PATH
```

## test
in folder becfuzz
```
mkdir output
make clean && make all
./BECFuzzDyninst64 -i /path/to/tcpdump -o ./output/tcpinst -b ./output/
./output/tcpinst -nr /path/to/input
```
run tcpdump without instrumenting
```
/path/to/tcpdump -nr /path/to/input
```


