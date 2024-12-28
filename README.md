# Kimberly Clark Document Extraction Pipeline
Repository to hold steps and pipeline construction scripts for document extraction and formatting

## Objective
Specification documents reside globally across different business units and regions (i.e. Brazil, China, Hygiene Products, Private Label Products, etc.) and are stored in a variety of both layout formats but also file formats (.docx, .pdf, .xlsx).
Documents will contain varying information that is relevant to the region's standards and the product lines specified within the documents. The goal is to convert as much information from these variety of documents into a single predictable source that will be pushed
to a new SAP global system, standardizing nomenclature, language, and required data points across all regions and product lines. The scripts/pipeline rely significantly on Microsoft's Azure AI Document Intelligence suite for layout determination, key:value pair extraction,
custom model training, and language translation. Processing and formatting of documents, or use of additional models, embeddings, will otherwise be done with python scripts retained in this repository. 

## General High-Level Framework
  1. Collect documents - Most documents will be sourced from internal EtQ system in mass extraction. Documents are almost always present in one of .pdf, .xlsx, .docx, .stl
  2. Classify documents - Estimated 20-30,000 documents will require extraction and analysis. Clustering documents in an unsupervised approach will provide the largest volumne of 'simliar' documents based on layout and context to be fed to Azure models
  3. Post processing - Post processing of output from the model to format into appropriate nomenclature and term mappings. Additional data wrangling and processing also to occur. 
