.. highlight:: sh

.. index:: ! Command-line options

.. _syntax:

Command-Line Syntax
================================

un-xtab.py should be run at the operating-system command line--i.e., at a 
shell prompt in Linux or in a command window in Windows.  Python may or 
may not need to be explicitly invoked, and the .py extension may or may 
not need to be included, depending on your operating system, operating 
system seetings, and how xtab is :ref:`installed <availability>`.

For Linux users: The xtab.py file contains a shebang line pointing to 
/usr/bin/python, so there should be no need to invoke the Python 
interpreter.  Depending on how un-xtab.py was obtained and installed, 
it may need to be made executable with the *chmod* command.

For Windows users: If you are unfamiliar with running Python programs 
at the command prompt, see https://docs.python.org/2/faq/windows.html.

In the following syntax descriptions, angle brackets identify required 
replaceable elements, and square brackets identify optional replaceable 
elements.

.. code-block:: sh

	un-xtab.py [options] <input_file_name> <output_file_name>

.. index:: Required arguments
   single: Arguments

Required Arguments
-------------------------------

.. code-block:: none

	<input_file_name>
			The name of the input file from which to read data. 
			This must be a text file, with data in a crosstabbed format.
			Details of the internal structure must be specified in the
			configuration file.
	<output_file_name>
			The name of the output file to create. The output file
			will be created as a .csv file.


.. index:: Optional arguments
   single: Arguments

Optional Arguments
-------------------------------

.. code-block:: none

	-c CONFIGFILE, --configfile=CONFIGFILE
			The name of the configuration file, with path if necessary.
			The default is a configuration file with the same name as the
			input file, but with an extension of ".cfg", in the same
			directory as the input file.
	-d, --displayspecs
			Print the format specifications that are allowed in the
			configuration file.
	-e ENCODING, --encoding=ENCODING
			Character encoding of the CSV file.  The value should be one of
			the strings listed at http://docs.python.org/library/codecs.html#standard-encodings
	-h, --help
			Show the built-in syntax help and exit.
	-n ROWSEQ, --number_rows=ROWSEQ
			A directive to number the rows of the output.  The value is the
			column header for the row numbers.
	-o, --outputheaders
			Print the output column headers, then exit.
	-p, --printconfig
			Pretty-print the configuration data after reading the configuration
			file, then exit.
	-s SPECNAME, --specname=SPECNAME
			The name of the set of specifications to use in the configuration file.
			The default is to use the name of the input data file, without
			its extension.

