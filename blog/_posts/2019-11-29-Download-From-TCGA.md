---
layout: post
title: Downloading histopathology data from the TCGA
description: >
  How to download TCGA samples with a script and a manifest.
sitemap: false
hide_last_modified: true
---


[The Cancer Genome Atlas](https://www.cancer.gov/about-nci/organization/ccg/research/structural-genomics/tcga), a landmark cancer genomics program, molecularly characterized over 20,000 primary cancer and matched normal samples spanning 33 cancer types. This joint effort between the National Cancer Institute and the National Human Genome Research Institute began in 2006, bringing together researchers from diverse disciplines and multiple institutions.

Over the next dozen years, TCGA generated over 2.5 petabytes of genomic, epigenomic, transcriptomic, and proteomic data. The data, which has already lead to improvements in our ability to diagnose, treat, and prevent cancer, will remain publicly available for anyone in the research community to use.




## Google storage of TCGA

The Cancer Genomics Cloud have put the TCGA ressource in a google cloud storage  `isb-tcga-phs000178-open` which allows fast and rapid access.

To make the most out of the ressource it is better to install the list of [google storage tools](https://cloud.google.com/storage/docs/gsutil).

## Downloading, tips
For automatic download, we create a file (a manifest.txt file) where we fill in the id and the filename for each patient, like below:
```
id  filename    md5 size    state
4a3346bc-8517-4672-b117-f17a50aec897    TCGA-AO-A0J2-01Z-00-DX1.7C9FEC7B-6040-4C58-9563-D10C0D7AC72E.svs    199b2ce15803c97c65d6d55fb5991af4    214678718   released
d2534d63-b497-44ab-9c60-99bbe29a5b48    TCGA-BH-A2L8-01Z-00-DX1.ACA51CA9-3C38-48A6-B4A9-C12FFAB9AB56.svs    fa017edacb3f14f2395620819cffd76b    2252985725  released 
```

To automatically download, you can then use the following command:
```bash
gsutil cp gs://isb-tcga-phs000178-open/gdc/${row.id}/${row.filename} .
```


## Aknowledgement

This post was written to keep this knowledge alive and was part of an older and deprecated project.
Judith Abécassis equally contributed.