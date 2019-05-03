# conservative_score
## 筛选人的保守性基因或区域

### 1.下载人保守性分数文件，包括基于phastcons和phylop两种算法获得的碱基保守性分值文件(*.wigFix.gz)，下载链接如下：
[phastCons100way](ftp://hgdownload.cse.ucsc.edu/goldenPath/hg19/phastCons100way/hg19.100way.phastCons/)

[phastCons46way](ftp://hgdownload.cse.ucsc.edu/goldenPath/hg19/phastCons46way)

[phyloP100way](ftp://hgdownload.cse.ucsc.edu/goldenPath/hg19/phyloP100way/hg19.100way.phyloP100way)

[phyloP46way](http://hgdownload.cse.ucsc.edu/goldenPath/hg19/phyloP46way/)
### 2.下载wigToBigWig和bigWigAverageOverBed软件，下载链接如下：
    
    http://hgdownload.cse.ucsc.edu/admin/exe/linux.x86_64/

### 3.将*.wigFix.gz转换成bw格式文件（请参考软件使用说明）

    wigToBigWig *.wigFix.gz chr_size.txt out.bw 
    
### 4.统计每个gene或region的平均保守性分值（请参考软件使用说明），一般score>=0.3表示为高保守性的基因。
    
    bigWigAverageOverBed  out.bw gene.bed gene.scores
    
