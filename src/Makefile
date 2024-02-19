PDFLATEX=dvipdfmx
LATEX=platex
BIBTEX=bibtex
DVI2PDF=dvipdfmx
TEXFILE=x2
MAINTEXFILES=p.tex

all: pdf
dvi: ${TEXFILE}.dvi
pdf: ${TEXFILE}.pdf

${TEXFILE}.dvi: ${TEXFILE}.tex ${MAINTEXFILES} ${TEXFILE}.bbl
	${LATEX} ${TEXFILE} && ${LATEX} ${TEXFILE}

${TEXFILE}.pdf: ${TEXFILE}.dvi
	${DVI2PDF} ${TEXFILE}.dvi
#${TEXFILE}.pdf: ${TEXFILE}.tex ${MAINTEXFILES} ${TEXFILE}.bbl
#	${PDFLATEX} ${TEXFILE} && ${PDFLATEX} ${TEXFILE}

${TEXFILE}.bbl:
	${LATEX} ${TEXFILE} && ${BIBTEX} ${TEXFILE}
bbl:
	${LATEX} ${TEXFILE} && ${BIBTEX} ${TEXFILE}

view:
	evince ${TEXFILE}.pdf &
clean:
	rm -f ${TEXFILE}.dvi ${TEXFILE}.pdf ${TEXFILE}.log ${TEXFILE}.aux ${TEXFILE}.bbl ${TEXFILE}.blg ${TEXFILE}.out texput.log
