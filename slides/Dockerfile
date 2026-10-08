FROM texlive/texlive:latest-small

RUN tlmgr update --self && tlmgr install \
    csquotes  \
    biblatex  \
    biber     \
    booktabs  \
    paratype  \
    etoolbox  \
    logreq    \
    pgf       \
    listings  \
    bussproofs \
    xcolor    \
    babel-portuges \
    hyphen-portuguese \
    && rm -rf /tmp/*
