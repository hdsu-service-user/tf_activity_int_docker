FROM hdsu/butchr

LABEL maintainer="Andres Quintero andres.quintero@bioquant.uni-heidelberg.de"


# Install macs2
RUN pip3.8 install macs2


######
# install annot
RUN R -e "BiocManager::install(c('BSgenome.Hsapiens.UCSC.hg19', 'EnsDb.Hsapiens.v75', 'GenomeInfoDbData', 'VariantAnnotation'), update = FALSE)"
RUN R -e "BiocManager::install(c('AnnotationFilter', 'biovizBase', 'ggbio', 'Rsamtools'), update = FALSE)"

# Install Seurat
RUN R -e "install.packages(c('Polychrome', 'Seurat'))"

# Install Signac
RUN R -e "install.packages(c('testthat'))"
RUN apt-get update && apt-get install -y \
    libglpk-dev \
    libgsl-dev
RUN R -e "install.packages(c('Signac'))"    
#RUN R -e "devtools::install_github('timoast/signac', ref = 'develop', upgrade='never')"
# 
# #install.packages("writexl")
# #devtools::install_version("RcppAnnoy", version = "0.0.16")
# #devtools::install_version("uwot", version = "0.1.8")
# 
# Install SCENIC
RUN R -e "BiocManager::install('RcisTarget', update = FALSE)"
RUN R -e "devtools::install_github('aertslab/AUCell', upgrade='never')"
RUN R -e "devtools::install_github('aertslab/SCENIC', upgrade='never')"
# 
# Install ARchR
RUN R -e "devtools::install_github('GreenleafLab/chromVARmotifs', upgrade='never')"
RUN R -e "devtools::install_github('immunogenomics/presto', upgrade='never')"

RUN apt-get update && apt-get install -y \
      libtiff-dev \
      libxt-dev
RUN R -e "devtools::install_github('GreenleafLab/ArchR', ref='master', repos = BiocManager::repositories(), upgrade='never')"
# 
# 
# 
RUN R -e "install.packages(c('umap'))"
RUN R -e "install.packages(c('doRNG'))"