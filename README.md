un-xtab.py
Desnormalizado de Datasets CSV em português

un-xtab.py um módulo python 2 e um programa de linha de comando
que rearranja dados desnormalizados para um formato normalizado.

Tome este exemplo:

| Estacao | 2006-05-23 | 2006-06-15 | 2006-07-19 |
|---------|------------|------------|------------|
| WQ-01   | 4.5        | 3.7        | 6.8        |
| WQ-02   | 9.7        | 5.1        | 7.2        |
| WQ-03   | 10         | 6.1        | 8.8        |

a forma desnormalizada resulta em

| Estacao | Data       | valor |
| ------- | ---------- | ----- |
| WQ-01   | 2006-05-23 | 4.5   |
| WQ-02   | 2006-05-23 | 3.7   |
| WQ-03   | 2006-05-23 | 6.8   |
| WQ-01   | 2006-06-15 | 9.7   |
| WQ-02   | 2006-05-15 | 5.1   |
| WQ-03   | 2006-06-15 | 7.2   |
| WQ-01   | 2006-07-19 | 10    |
| WQ-02   | 2006-07-19 | 6.1   |
| WQ-03   | 2006-07-19 | 8.8   |

Tanto a entrada quanto a saida são dados em formato CSV

como se executa na linha de comando:

```bash
# linux
python un-xtab.py -c ../doc/exemplos/configuracao.conf \
-s exemplo1 \
../doc/exemplos/planilha_entrada.csv \
../doc/exemplos/saida.csv

```

```cmd
# windows
python un-xtab.py -c ..\doc\exemplos\configuracao.conf ^
-s exemplo1 ^
..\doc\exemplos\planilha_entrada.csv ^
..\doc\exemplos\saida.csv

```


Opções e sintaxe
================================

```
  un-xtab.py [options] input_file_name output_file_name 

Arguments: 
  Input file name     The name of a text (CSV) file with crosstabbed data. 
  Output file name    The name of a text (CSV) to create with normalized data. 

Options:
  --version           Show program's version number and exit 
  -h, --help          Show this help message and exit 
  -c CONFIGFILE, --configfile=CONFIGFILE 
                      The name of the config file, with path if necessary. 
                      The default is to look for a configuration file with 
                      the same name as the input file, but with an extension 
                      of cfg, in the same directory as the input file. 
  -d, --displayspecs  Print the format specifications allowed in the 
                      configuration file, then exit.
  -e ENCODING, --encoding=ENCODING 
                      Character encoding of the CSV file. It should be one of 
                      the strings listed at http://docs.python.org/library/
                      codecs.html#standard-encodings.
  -n ROWSEQ, --number_rows=ROWSEQ
                      Add a sequential number to each output row, with a
                      column header of ROWSEQ.
  -o, --outputheaders Print the output column headers, then exit.
  -p, --printconfig   Pretty-print the configuration data after reading the
                      configuration file, then exit.
  -s SPECNAME, --specname=SPECNAME 
                      The name of the section to use in the configuration 
                      file. The default is to use the name of the input data file,
                      without its extension.
```

Projeto original disponível em `OSDN <http://un-xtab.osdn.io/>`_.
