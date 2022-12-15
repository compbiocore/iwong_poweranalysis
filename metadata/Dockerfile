#FROM fdewes/rstudio-server-arm64:latest
FROM rocker/rstudio:latest

RUN R -e "install.packages(c('evaluate', 'digest', 'highr', 'markdown', 'strings', 'yaml', 'Rcpp', 'htmltools', \
    'caTools', 'bites', 'knitr', 'jsonlite', 'base64enc', 'rprojroot', 'rmarkdown', 'KernSmooth', 'MASS', 'Matrix',  \
    'boot', 'class', 'cluster', 'codetools', 'lattice', 'mgcv', 'nlme', 'nnet', 'rpart', 'spatial', 'survival', 'BiocManager'), \
    dependencies=TRUE,repos='http://cran.rstudio.com/')"
RUN R -e "install.packages('https://cran.r-project.org/src/contrib/Archive/locfit/locfit_1.5-9.4.tar.gz', repos=NULL, type='source')"
RUN R -e "BiocManager::install(c('edgeR', 'RnaSeqSampleSize', 'xlsx', 'tidyr', 'AnnotationHub'))"
RUN R -e "BiocManager::install(c('FactoMineR'))"
RUN apt-get update
RUN apt-get install -y libz-dev
RUN R -e "BiocManager::install(c('DESeq2'))"
#RUN apt-get install -y pandoc-citeproc
RUN mkdir /poweranalysis
RUN chmod 777 -R /poweranalysis
RUN cd /poweranalysis && git clone https://github.com/compbiocore/iwong_poweranalysis.git