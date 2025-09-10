# Makefile для сборки отчёта

# Ищем все .md файлы в текущей директории и формируем из них цели для pdf и docx
MD_FILES = $(wildcard *.md)
PDF_FILES = $(MD_FILES:.md=.pdf)
DOCX_FILES = $(MD_FILES:.md=.docx)

# Фильтры для pandoc (для cross-reference и библиографии)
FILTERS = --filter pandoc-crossref

# Цель по умолчанию - собрать всё
all: $(PDF_FILES) $(DOCX_FILES)

# Правило для конвертации .md в .pdf
%.pdf: %.md
	pandoc "$<" $(FILTERS) -o "$@"

# Правило для конвертации .md в .docx
%.docx: %.md
	pandoc "$<" $(FILTERS) -o "$@"

# Очистка сгенерированных файлов
clean:
	rm -f $(PDF_FILES) $(DOCX_FILES) *~

# Псевдоцель, чтобы make не путал её с реальным файлом
.PHONY: all clean
