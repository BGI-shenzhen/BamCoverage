# BamCoverage
<b>BamCoverage: A efficient software tools to Calculate site depth of genome based  bam/sam List</b>

</br></br></br>
The newest version of this funtion was integrated into toolkit <b>[BamDeal](https://github.com/BGI-shenzhen/BamDeal) </b>,please replace BamCoverage by this <b>[BamDeal](https://github.com/BGI-shenzhen/BamDeal)</b>.

```php
           ./BamDeal statistics  Coverage
```

</br></br>

1) Install
------------

Please replace BamCoverage with this toolkit <b>[BamDeal](https://github.com/BGI-shenzhen/BamDeal)</b>.

</br></br></br>

1) Install
------------

  This software rely htslib，so should Pre-install htslib first [samtools-1.5/htslib-1.5](https://sourceforge.net/projects/samtools/files/samtools)
  </br>Then Just  [make]  or [sh  make.sh ]  to compile this software.
  </br>the final software can be found in the Dir [bin/BamCoverage]

 For <b>linux /Unix </b> and <b>macOS </b>
<pre>
        tar -zxvf  BamCoverage-XXX.tar.gz
        cd BamCoverage-XXX;                             # if Link do not work ,Try <b>re-install</b>  two  library
        cd src;                                         #【zlib and htslib】 and copy them to the library Dir
        make ; make clean                               # BamCoverage-XX/src/include/zlib 
        ../bin/BamCoverage                              
</pre>
</br>


2) Example
------------
* 1) Calculate bam files
```
#To Calculate bam

    ./bin/BamCoverage  -List  bam.list  -OutPut  out.depth.fa.gz -MinQ -1
   # To out Put the each chr meanDepth Coverage add [-Stat]
    ./bin/BamCoverage  -List  bam.list  -OutPut  out.depth.fa.gz  -Stat

```

* 2) Calculate sam files
```
# To cCalculate sam
	./bin/BamCoverage  -List  sam.list  -OutPut  out.depth.fa.gz  -Stat
# Also you the  add the  -MinQ to filter some reads
	./bin/BamCoverage  -List  sam.list  -OutPut  out.depth.fa.gz  -MinQ 10
```

* 3) Calculate GC-Depth Dis Figure
```
# First Out Put the Depth-GC wig info with [-Ref  Ref.fa]
	./bin/BamCoverage  -List bam.list   -OutPut outFix   -Ref Ref.fa  -Stat
# Second To Plot the Figure 
# Must PreInstall R with library ggplot2,gridExtra,ggExtra
	perl  bin/GC_Depth_Plot.pl  outFix.DepthGC.wig.gz  MaxDepth  OutFig
```

3) Introduction
------------

* <b> Parameter description</b>

```php

  ./BamDeal   statistics  Coverage

        Usage: Coverage  -List  <bam.list>  -OutPut  <outFix>

                -InList    <str>     Input Bam/Sam File List
                -InFile    <str>     Input Bam/Sam File File[repeat]
                -OutPut    <str>     OutPut File prefix

                -Ref       <str>     In Ref.fa If Want Out Depth-GC wig info
                -Windows   <int>     Windows size for Depth-GC wig[10000]
                -Bed       <str>     Stat Coverage,MeanDepth for these bed Regions
                -Stat                Stat Coverage,MeanDepth & Depth Dis of whole-genome

                -MinQ      <int>     Filter the read low mapQ[10]

                -help                Show this help [hewm2008 v1.30]

```

4) Results
------------
Format Introduction

* [sam bam format](https://samtools.github.io/hts-specs/SAMv1.pdf)

5）Discussing
------------
- email: hewm2008@gmail.com / hewm2008@qq.com
- join the<b><i> QQ Group : 125293663</b></i>



######################swimming in the sky and flying in the sea ########################### ##


