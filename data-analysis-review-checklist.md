## Data analysis review checklist

### Reviewer: zywkloo

### Conflict of interest

- [x] As the reviewer I confirm that I have no conflicts of interest for me to review this work.

### Code of Conduct

- [x] I confirm that I read and will adhere to the [MDS code of conduct](https://ubc-mds.github.io/resources_pages/code_of_conduct/).

### General checks

- [x] **Repository:** Is the source code for this data analysis available? Is the repository well organized and easy to navigate?
- [x] **License:** Does the repository contain a plain-text LICENSE file with the contents of an [OSI approved](https://opensource.org/licenses/alphabetical) software license?

### Documentation

- [x] **Installation instructions:** Is there a clearly stated list of dependencies? 
- [x] **Example usage:** Do the authors include examples of how to use the software to reproduce the data analysis?
- [x] **Functionality documentation:** Is the core functionality of the data analysis software documented to a satisfactory level?
- [x] **Community guidelines:** Are there clear guidelines for third parties wishing to 1) Contribute to the software 2) Report issues or problems with the software 3) Seek support

### Code quality
- [ ] **Readability:** Are scripts, functions, objects, etc., well named? Is it relatively easy to understand the code?
- [x] **Style guidelides:** Does the code adhere to well known language style guides?
- [x] **Modularity:** Is the code suitably abstracted into scripts and functions?
- [ ] **Tests:** Are there automated tests or manual steps described so that the function of the software can be verified? Are they of sufficient quality to ensure software robsutness?

### Reproducibility
 
- [x] **Data:** Is the raw data archived somewhere? Is it accessible?
- [x] **Computational methods:** Is all the source code required for the data analysis available?
- [x] **Conditions:** Is there a record of the necessary conditions (software dependencies) needed to reproduce the analysis? Does there exist an easy way to obtain the computational environment needed to reproduce the analysis?
- [x] **Automation:** Can someone other than the authors easily reproduce the entire data analysis?

### Analysis report

- [x] **Authors:** Does the report include a list of authors with their affiliations?
- [x] **What is the question:** Do the authors clearly state the research question being asked?
- [x] **Importance:** Do the authors clearly state the importance for this research question?
- [x] **Background**: Do the authors provide sufficient background information so that readers can understand the report?
- [x] **Methods:** Do the authors clearly describe and justify the methodology used in the data analysis? Do the authors communicate any assumptions or limitations of their methodologies?
- [x] **Results:** Do the authors clearly communicate their findings through writing, tables and figures?
- [x] **Conclusions:** Are the conclusions presented by the authors correct? 
- [x] **References:** Do all archival references that should have a DOI list one (e.g., papers, datasets, software)?
- [x] **Writing quality:** Is the writing of good quality, concise, engaging? 

### Estimated hours spent reviewing: 

1.5 hours

### Review Comments: 

Please provide more detailed feedback here on what was done particularly well, and what could be improved. It is especially important to elaborate on items that you were not able to check off in the list above.

1. As shown in the image below, the `src` directory only contains 1 file. In that case, all test cases trying to call the helpers from `src/` would not be executed, as they will fail in the dependency import stage (most likely).
![image](https://github.com/zywkloo/data-analysis-review-checklist/assets/18610590/5f27579d-1745-4982-9e79-f12ca5daa0ed)

2. The test files could have more consistent naming standard, like `test-word1_word2_word3.py`<img width="325" alt="image" src="https://github.com/zywkloo/data-analysis-review-checklist/assets/18610590/b7183e15-447b-4556-9597-8b0ec3bc78dd">

3. May consider referencing the `environment.yaml` in the docker file, to enhance the code reusability.
  For example:
```
  FROM quay.io/jupyter/minimal-notebook:2023-11-22

  WORKDIR /home/jovyan
  
  COPY environment.yaml .
  
  RUN conda env update --file environment.yaml
```
Despite some minor naming and importing issues, this project stands out for comprehensive documentation, code quality, reproducibility, and thorough analysis reporting.

#### Attribution

This was derived from the [JOSE review checklist](https://openjournals.readthedocs.io/en/jose/review_checklist.html) and the ROpenSci review checklist.
