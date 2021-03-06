GASiC Metagenomics Workflow
===========================

<b>G</b>enome <b>A</b>bundance <b>Si</b>milarity <b>C</b>orrection workflow.

Description
-----------

One goal of sequencing based metagenomic analysis is the quantitative taxonomic assessment of microbial community compositions. However, the majority of approaches either quantify at low resolution (e.g. at phylum level) or have severe problems discerning highly similar species. Yet, accurate quantification on species level is desirable in applications such as metagenomic diagnostics or community comparison. GASiC is a method to correct read alignment results for the ambiguities imposed by similarities of genomes. It has superior performance over existing methods.

![alt tag](metagenomics_gasic_workflow.png)

Prerequisites
-------------

Make sure that the following prerequisites are installed:
- SeqAn NGS ToolBox (see [installation instructions](http://trac.seqan.de/wiki/HowTo/UseSeqAnNodesInKnime#InstallSeqAninKNIME))
- KNIME R Statistics Integration (*KNIME Desktop Update Site* --> *KNIME & Extensions*)
- A working R installation

Example Data
------------

Extract the bee_example.zip file and configure the two *Input File* nodes accordingly:

<dl>
  <dt>Reads</dt>
  <dd><ul>
  <li>SRR059298_72_subset.fasta</li>
  </ul>
  First 100k x 72bp reads of <href="http://sra.dnanexus.com/runs/SRR059298">SRR059298</href> dataset. Whole viral genome sequence from bees infected by Varroa mites from WHRI apiary 2009.</dd>
  <dt>Genomes</dt>
  <dd><ul>
  <li>dwv.fasta</li>
  <li>vdv-1-dwv-5.fasta</li>
  <li>vdv-1-dwv-9.fasta</li>
  <li>vdv1.fasta</li>
  </ul>
  Deformed wing virus (DWV), Varroa destructor virus-1 (VDV1) and recombinants of both.</dd>
</dl>  

Output
------

The result of the GASiC workflow is a table that for each genome gives the number of mapped reads (observed read counts), corrected reads, estimated error, p-value and normalized abundance.

Additionally an R-plot shows the observed and corrected reads counts. The example above would give the following plot:

![alt tag](bee_example.png)

Contact
-------

If you have any further questions or comments please contact:
 * [Stephan Aiche](mailto:stephan.aiche@fu-berlin.de)
 * [Jochen Singer](mailto:jochen.singer@fu-berlin.de)

References
----------

**GASiC Website:**
  http://sourceforge.net/projects/gasic/
  
**Original Paper:**
  Martin S. Lindner and Bernhard Y. Renard. *Metagenomic abundance estimation and diagnostic testing on species level*, Nucl. Acids Res. 2013, 41(1): e10, [doi:10.1093/nar/gks803](http://nar.oxfordjournals.org/content/41/1/e10)
