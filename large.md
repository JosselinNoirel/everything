# Tracking a large file

* [Git Large File Storage](https://git-lfs.github.com/) can be installed with brew
* The large file is modified from the [sample.sam.gz](https://s3.amazonaws.com/samtools-tutorial/sample.sam.gz), which is used in the [samtools tutorial](http://quinlanlab.org/tutorials/samtools/samtools.html)

There are over 5 million reads in the original file, so we reduce this to just under a million.

```
$ gunzip sample.sam.gz
$ head -1000000 sample.sam > small.sam
$ samtools view -Sb small.sam > small.bam
```