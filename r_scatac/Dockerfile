FROM hdsu/butchr

LABEL maintainer="Andres Quintero andres.quintero@bioquant.uni-heidelberg.de"


# Install macs2
RUN pip3.8 install macs2


######

# Install Seurat
RUN R -e "install.packages(c('Polychrome', 'Seurat'))"
RUN R -e "devtools::install_github('timoast/signac', ref = 'develop')"

#install.packages("writexl")
#devtools::install_version("RcppAnnoy", version = "0.0.16")
#devtools::install_version("uwot", version = "0.1.8")


# install annot
RUN R -e "BiocManager::install(c('BSgenome.Hsapiens.UCSC.hg19', 'EnsDb.Hsapiens.v75', 'GenomeInfoDbData', 'VariantAnnotation'), update = FALSE)"

# Install ARchR
RUN R -e "devtools::install_github('GreenleafLab/ArchR', ref='master', repos = BiocManager::repositories())"
RUN R -e "devtools::install_github('GreenleafLab/chromVARmotifs')"
RUN R -e "devtools::install_github('immunogenomics/presto')"

# Install SCENIC
RUN R -e "BiocManager::install('RcisTarget', update = FALSE)"
RUN R -e "devtools::install_github('aertslab/AUCell')"
RUN R -e "devtools::install_github('aertslab/SCENIC')"


