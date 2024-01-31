# tfsites.AffinityScan v1

**Author(s):** Joe Solvason  

**Contact:** Joe Solvason (solvason@eng.ucsd.edu)

**Adapted as a GenePattern Module by:** Ted Liefeld (jliefeld@cloud.ucsd.edu)

**Task Type:** Transciption factor analysis

**LSID:**  urn:lsid:genepattern.org:module.analysis:00446


## Introduction

`affinityScan` reports the median fluorescence intensity (MFI) from a raw PBM dataset of every possible k-mer in a sequence on a line graph. This shows the binding preferences for a transcription factor across a given sequence. 

## Methodology

The raw PBM dataset for a transcription factor is downloaded from uniPROBE. We iterate across every k-mer in the given sequence and obtain its MFI from the PBM dataset. The MFI for each k-mer is plotted on a graph at the first nucleotide of the k-mer. 

## Parameters

<span style="color: red;">*</span> indicates required parameter

### Inputs and Outputs: 

- <span style="color: red;">*</span> **Raw PBM Input (.txt)**
    - Input file containing the raw PBM dataset for the first transcription factor of interest obtained from uniPROBE. 
- <span style="color: red;">*</span> **Line Graph of MFI Across a Sequence (.png)**
    -  Name of the output file containing the line graph of the MFI signal of k-mers across a sequence. 
 
### Other Parameters:

- <span style="color: red;">*</span> **Header Present (boolean)**
    - If `True`, a header exists in the input PBM data file. If `False`, no header exists.
- <span style="color: red;">*</span> **Column Index of DNA K-mers (integer)**
    - Number of the column containing the forward DNA sequence in the input PBM file. (1-indexed, 1 is the first column)
- <span style="color: red;">*</span> **Column Index of MFI (integer)**
    - Number of the column containing the MFI signal in the input PBM file. (1-indexed, 1 is the first column)
- <span style="color: red;">*</span> **Sequence (string)**
    - DNA sequence to scan for k-mers
- **Zoom Window (dash-separated string)**
    - `Default = None`
    - Given a start position and an end position, zoom into a portion of the sequence. The numbers in the range are inclusive. For example, the first 200 nucleotides of the sequence would be specified as: 1-200.
- **Fill Color (string)**
    - `Default = None`
    - Select the color to fill the area under the line graph, otherwise it will not be filled.
- **Plot Resolution (integer)**
    - `Default = 200`
    - Resolution of the plot, in dots (pixels) per inch.


## Input Files

1.  Raw PBM Input (.tsv)
    - Columns
        - `8-mer:` every possible forward k-mer sequence with length k
        - `8-mer:` the reverse complement of the forward k-mer
        - `E-score:` the enrichment score of the k-mer
        - `Median:` the median fluorescence intensity of the k-mer
        - `Z-score:` the z-score of the k-mer 

   <img src="./01-input.png"/> 
       
## Output Files

1. Normalized PBM data (.tsv)
   - Columns
       - `Seq:` the sequence of every possible k-mer
       - `Rel_aff:` the relative affinity of the k-mer normalized to the max IUPAC k-mer

2. Histograms of Relative Affinities (.png) 
    - Histogram plots
        - All relative affinity values
        - Affinity values for the sequences that follow the IUPAC minimal binding site
        - Affinity values for the sequences that don't follow the IUPAC minimal binding site

    
  
## Example Data

Example input data is available on github at [https://github.com/genepattern/tfsites.AffinityScan/tree/develop/gpunit/data](https://github.com/genepattern/tfsites.AffinityScan/tree/develop/gpunit/data)
    
## References

    
## Version Comments

- **1.0.0** (2023-11-28): Initial draft of document scaffold.