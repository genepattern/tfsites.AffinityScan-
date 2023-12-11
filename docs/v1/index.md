# tfsites.AffinityScan v1

**Author(s):** Joe Solvason  

**Contact:** Joe Solvason (solvason@eng.ucsd.edu)

**Adapted as a GenePattern Module by:** Ted Liefeld (jliefeld@cloud.ucsd.edu)

**Task Type:** Transciption factor analysis

**LSID:**  urn:lsid:genepattern.org:module.analysis:00446


## Introduction

tfsites.AffinityScan  returns a distribution of the MFI signal across a sequence.

## Functionality

TBD

## Methodology

TBD

## Parameters

<span style="color: red;">*</span> indicates required parameter

- **pbm data**<span style="color: red;">*</span>
    - This is a [ state what the format and content is supposed to be] list of SNVs to be analyzed.
- **header.present**<span style="color: red;">*</span>
    -  TRUE/FALSE, genomic coordinates are 0-indexed 
- **out filename**<span style="color: red;">*</span>
    - Out file name for the annotated PBM data
- **header.sequence.present**
    - TRUE/FALSE, Is there a header sequence in the raw PBM file?.
- **column.forward**
    - Column of the forward DNA sequence in the pbm file (1-indexed).
- **column.MFI**
    - Column of the MFI in the pbm file (1-indexed).
- **sequence**
    - Sequence to be scanned.
- **plot.resolution**
    - Plot resolution in DPI.
- **zoom**
    - Zoom into the plot by the number of base pairs.


## Input Files

1.  pbm data.   [ define format and contents in detail ] 
    

       
## Output Files

  1.line plot: <output filename>.png.  [ describe the plot contennts here ]
  
  <img src="./06-output_zrs-enhancer-signal.png"/>
    
  
## Example Data

Example input data is available on github at [https://github.com/genepattern/tfsites.AffinityScan/tree/develop/gpunit/data](https://github.com/genepattern/tfsites.AffinityScan/tree/develop/gpunit/data)
    
## References

    
## Version Comments

- **1.0.0** (2023-11-28): Initial draft of document scaffold.
