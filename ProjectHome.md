[Cocoatron](http://cocoatron.com)

The suite of Automator Actions for Mac OS X that brings drag-and-drop simplicity to creating and automating complex XML Processing Pipelines.'

To install, download Cocoatron and unzip. Then drag the Cocoatron .action and .definition files to ~/Library/Automator. You may need to create this folder.
Inspired by XProc and SXPipe, Cocoatron is a simple way to create XML pipelines visually - without writing a line of custom 'glue' code in Java, C++ or other languages.

Conceptually, Cocoatron is a combination of XProc and Apple's Automator application. XProc is the W3C's spec for high-level descriptions of XML processing pipelines. Automator is Apple's graphical application for creating scripting pipelines with drag-and-drop simplicity.

Cocoatron consists of six Automator Actions (composeable, configurable pipeline stages):

  * Load XML Documents
  * Process XIncludes of XML Documents
  * Validate XML Documents (DTD, XSD, RNG)
  * Transform XML Documents (XSLT)
  * Query XML Documents (XQuery)
  * Serialize XML Documents

Implemented using the powerful libxml2 framework, Cocoatron includes support for XInclude, XSLT 1.0, EXSLT, XQuery, and validation against DTD, W3C XML Schema, and RELAX NG XML syntax..

Much like SXPipe, these actions deal strictly with XML Infosets. Under the hood, the XML Infosets created and returned by Cocoatron Actions are actually libxml2 xmlDocPtr structs contained in Cocoa object wrappers. An Infoset is constructed using Load XML Documents and serialized back to text using Serialize XML Documents. To create pipleines, place other, built-in Apple Actions before and after these two Actions.

For example, start an XML pipeline with local XML documents using Get Specified Finder Items (Finder) or remote ones using Get Specified URLs (Safari). Finish a pipleine with New Text File (Finder) or New TextEdit Document (TextEdit).

Each Cocoatron Action includes a collapsable Console text field that will show you any errors or warnings that occur during that Aciton's processing. This allows for easy debugging.

As compared to the Beta release last week, v1.0 significantly improves behavior of Load XML Documents and fixes a nasty bug where dragging a Cocoatron Action into a Workflow would temporarily disable the 'Run' button.


Implementation Details

Cocoatron is written in Objective-C and C, and is based on:

libxml
libxslt
libexslt
Apple's Cocoa Frameworks
Apple's NSXML Framework
Cocoatron requires Mac OS X 10.4 Tiger or later.

Cocoatron is developed by Todd Ditchendorf. Have feedback? Email me.