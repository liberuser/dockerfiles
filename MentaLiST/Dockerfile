FROM julia:1.3
ENV JULIA_DEPOT_PATH=/opt/julia
ENV JULIA_PKGDIR=/opt/julia

RUN julia -e 'using Pkg; Pkg.add.(["Distributed", "ArgParse", "BioSequences", "JSON", "DataStructures", "JLD", "GZip", "Blosc", "FileIO", "TextWrap", "LightXML"])'

RUN curl -L -O https://github.com/liberuser/MentaLiST/archive/latest.tar.gz \
 && tar -zxvf latest.tar.gz -C /opt MentaLiST-latest \
 && rm -rf latest.tar.gz \
 && chmod -R a+rwx /opt

RUN rm -rf /usr/local/bin \
 && ln -s /opt/MentaLiST-latest/src/ /usr/local/bin

ENTRYPOINT ["bash"]
