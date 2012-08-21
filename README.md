ePub-Boilerplate
================

This boilerplate provides a complete template for generating ePub-formatted books. It includes all the standard sections of a book (eg. table of contents, prologue, etc), descriptions of their use and contains examples of ePub features at work (eg. end notes, index, etc)

Fork of http://javierarce.github.com/epub-boilerplate

## Book Template

The structure below is included in the boilerplate and it conforms to the standard structure of [book design](http://en.wikipedia.org/wiki/Book_design). It is common practice to follow the order described here.

Not all books require every section and in some cases some sections can be merged into one (eg. _preface_ and _acknowledgment_).

1. **Front matter**
	* Cover
	* Title
	* Edition Notice
	* Dedication
	* Table of Contents
	* List of Illustrations
	* List of Tables
	* Foreword
	* Preface
	* Acknowledgements
	* Epigraph
	* Introduction
	* Prologue

2. **Body matter**
	* PART I
		* Chapter 1
		* Chapter 2
	* PART II
		* Chapter 3
		* Chapter 4
	* PART III
		* Chapter 5
		* Chapter 6

3. **Back matter**
	* Epilogue
	* Afterword
	* Addendum
	* End Notes
	* Glossary
	* Bibliography
	* Index
	* Colophon

## How to use it

1. Get the template:

        $ git clone git@github.com:javierarce/epub-boilerplate.git

2. Edit the contents of the `book` directory.

3. Run the publish script to generate and validate the book:

        $ ./publish book.epub

## Editing the book template

* File `TOC.xhtml` 

	* Edit meta tag `dtb:uid` to reflect your unique identifier (uuid, isbn, etc)

			<meta content="urn:isbn:[ISBN]" name="dtb:uid"/>

	* Edit the content depth

			<meta content="1" name="dtb:depth"/>

	* Edit with the title of the book

			<docTitle>
				<text>[BOOK'S TITLE]</text>
			</docTitle>

	* Describe the structure of your book with `navPoint` nodes and subnodes.

* Folder `Text-Frontmatter`
	* Edit the cover, title, table of content, etc.
	* If needed remove unnecesary sections.
	
* Folder `Text`
	* Create the proper book structure using parts/volumes and chapters.
	 
* Folder `Text-Backmatter`
	* Edit the appropiate sections.
	* If needed remove unnecesary sections.

* File `CONTENT.opf`
	* Enter the metadata of the book under `metadata`
	* Enter the full list of files used in the book under `manifest`
	* Enter the order in which the text files should appear under `spine`
	* Enter the role of each file type under `guide`

## ePub validation

This project uses epubcheck to validate the generated ePubs. If the build.sh script complains when running epubcheck, make sure you have java installed and it's in your PATH.

If you need help running epubcheck read this <a href="http://blog.threepress.org/2010/12/16/running-epubcheck-on-your-computer/">step-by-step guide</a>.

## Using the check script to validate the book.

    $ ./check book.epub
    
## Style

Basic styles have been added to the `style.css` file to accomodate for standard layouts of the sections included.

For more advanced styles have a look at the <a href="https://github.com/mattharrison/epub-css-starter-kit">ePub CSS Starter Kit</a>.

## Useful resources
      
* [ePub 2.0 Publication specs](http://idpf.org/epub/20/spec/OPS_2.0.1_draft.htm)
* [ePub 2.0 OPF Package Document specs](http://idpf.org/epub/20/spec/OPF_2.0.1_draft.htm)
* [ePub 3.0 spec](http://idpf.org/epub/30)
* [Device compatibilty chart](http://wiki.mobileread.com/wiki/Device_Compatibility)
* [ePub CSS Starter Kit](https://github.com/mattharrison/epub-css-starter-kit)
* [ePub Validator](http://code.google.com/p/epubcheck)
* [UUID generator](http://www.famkruithof.net/uuid/uuidgen)
* [BISAC Subject Headings List](http://www.bisg.org/what-we-do-0-136-bisac-subject-headings-list-major-subjects.php)
* [Practical ePub metadata: Authorship](http://blog.threepress.org/2009/11/27/practical-epub-metadata-authorship/)
* [MARC Code List for Relators](http://www.loc.gov/marc/relators)
* [What Is EPUB 3? An Introduction to the EPUB Specification for Multimedia Publishing](http://shop.oreilly.com/product/0636920022442.do)
