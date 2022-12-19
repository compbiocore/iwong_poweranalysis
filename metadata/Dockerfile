#FROM fdewes/rstudio-server-arm64:latest
#FROM rocker/rstudio:4.2.2
#RUN R -e "install.packages(c('evaluate', 'digest', 'highr', 'markdown', 'strings', 'yaml', 'Rcpp', 'htmltools', \
#    'caTools', 'bites', 'knitr', 'jsonlite', 'base64enc', 'rprojroot', 'rmarkdown', 'KernSmooth', 'MASS', 'Matrix',  \
#    'boot', 'class', 'cluster', 'codetools', 'lattice', 'mgcv', 'nlme', 'nnet', 'rpart', 'spatial', 'survival', 'BiocManager'), \
#    dependencies=TRUE,repos='http://cran.rstudio.com/')"
#RUN R -e "install.packages('https://cran.r-project.org/src/contrib/Archive/locfit/locfit_1.5-9.4.tar.gz', repos=NULL, type='source')"
#RUN apt-get update
#RUN apt-get install -y libxt6 liblzma-dev libbz2-dev libz-dev
#RUN R -e "BiocManager::install(c('edgeR', 'RnaSeqSampleSize', 'xlsx', 'tidyr', 'AnnotationHub'))"
#RUN R -e "BiocManager::install(c('FactoMineR'))"
#RUN apt-get install -y pandoc-citeproc
#RUN cd /home/rstudio && git clone https://github.com/compbiocore/iwong_poweranalysis.git
#RUN chmod 777 -R /home/rstudio/iwong_poweranalysis/

FROM cowmoo/rnaseq_rstudio:latest
RUN apt-get update
RUN apt-get install -y libxt6 liblzma-dev libbz2-dev libz-dev
RUN R -e "BiocManager::install(c('RnaSeqSampleSize'))"
RUN cd /home/rstudio && git clone https://github.com/compbiocore/iwong_poweranalysis.git
RUN chmod 777 -R /home/rstudio/iwong_poweranalysis/
