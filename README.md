# Demux
This repository has commands and samplesheets used for demultiplexing
## 1. Demultiplexing the umi tagged sequences 

### Use the following command if index1 has a 8 base umi at the end 
The read structure was 151,16,10,151
```
bcl2fastq -R 230215_M04898_0087_000000000-DJG93 -o 230215_M04898_0087_000000000-DJG93/demux_out/ --sample-sheet Samplesheet_delN_16Feb2023.csv --use-bases-mask Y151,I8,Y8,I8nn,Y151 --mask-short-adapter-reads 0
```
The RunInfo.xml file needs to be modified
original
```
<Read Number="1" NumCycles="151" IsIndexedRead="N" IsReverseComplement="N"/>
<Read Number="2" NumCycles="16" IsIndexedRead="Y" IsReverseComplement="N"/>
<Read Number="3" NumCycles="10" IsIndexedRead="Y" IsReverseComplement="Y"/>
<Read Number="4" NumCycles="151" IsIndexedRead="N" IsReverseComplement="N"/>
```
modified 
```
<Read Number="1" NumCycles="151" IsIndexedRead="N" IsReverseComplement="N"/>
<Read Number="2" NumCycles="8" IsIndexedRead="Y" IsReverseComplement="N"/>
<Read Number="3" NumCycles="8" IsIndexedRead="N" IsReverseComplement="N"/>
<Read Number="4" NumCycles="10" IsIndexedRead="Y" IsReverseComplement="Y"/>
<Read Number="5" NumCycles="151" IsIndexedRead="N" IsReverseComplement="N"/>
```
