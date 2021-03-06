# Intro to PHP extensions
- Derick Rethans
- [Talk Slides](https://joind.in/22362)
- Agenda
	- what are extensions
		- addtional functions and classes
		- dictributed through PECL or distributed seperatately.
	- Why write an extension
		-  wrap existing library
		- wrapping libraries
			- image recognition
				- OpenCV, Dlib
			- database driver
			- image processing
				- GD, Cairo, ImageMagick 
		- Impossible in userland
			- sharing data between requests
		- Speed
			- PHP is fast but things can be faster
	- Why not write an extension
		- takes more time to write, debug, and maintain
	- What makes up an extension
		- config.m4/config.w32
			- config options and build instructions
		- php_extension.h
			- header files and glue
		- extension.c
			- extension definition and function implementation
		- algorithms.c
			- C implementation of algorithms
		- tests/*.phpt
			- Tests written in PHP
	- config.m4
		- build instructions
		- PHP_ARG_ENABLE for internal library
		- PHP_ARG_ for external library
	- config.w32 (build instructions for windows)
		- ARG_ENABLE
	- Building the extension
		- phpize
			- brings in headers and creates config script
		- ./configure
			- Runs system checks, and creates Makefile
			- platform dependent
		- make
			- Builds the extension
	- header file
		- Guard
			- file only gets included once
			- define version
		- Module Definition
			- needs to find shared objects
		- Module initialiser declarations
			- MINFO 
			- MINIT
		- Forward declarations
			- C cannot use a function unless you declare or define it this declarion is called forward declaration.
	- Extension Set-Up
		- Header inclusions
		- Argument Information
		- List of Functions
	- Module Set-Up
		- Module (extension) definition:
			- module api number can be replaced with php version number
			- first parameter is exenstion
		- Handle shared 
	- Extension Set-Up
		- module initialisation
			- register constants
			- make sure to return success constant
		- module info
			- shows info
	- Implementing the function
		- parse input parameters
			- zend_parse_parameters
				- A format letter for every type
				- match with a C data type
				- Cleaned up for you
		- convert data into right format
		- run algo
		- return result