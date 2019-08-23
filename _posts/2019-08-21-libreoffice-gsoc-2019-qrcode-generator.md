---
layout: post
title: GSoC'19 LibreOffice - QR Code Generation Final Report
---

## Describe my work briefly

* Integrate a QR Code generating Library.
* Provide a platform to generate QR Code in LibreOffice apps.

## What code got merged.

* Integrate the QR generating Library.
    
    An [external Library][nayuki's-library] was shipped with LibreOffice.  
    Link to work: [bundle external](https://gerrit.libreoffice.org/#/c/73302/)  

* Implemented a QR Code Dialog Box.

    The Dialog Box takes the inputs needed for generating the QR Code and produce the QR codes  
    Link to work: [QR Dialog Box](https://gerrit.libreoffice.org/#/c/74167/)  

    Fix associated with above topic  
    [Add qrcodegen ui file to make file](https://gerrit.libreoffice.org/#/c/76376/)   
    [Make generated QR Code as a perfect square](https://gerrit.libreoffice.org/#/c/76954/)   
    [Fix: Border feature QR Code](https://gerrit.libreoffice.org/#/c/76953/)  
    [Error Correction in QR Code](https://gerrit.libreoffice.org/#/c/76958/)    
    [Reduce default border value in the QRCode Dialog](https://gerrit.libreoffice.org/#/c/77868/)

* Made QR code Dialog Box callable in LO apps.

    The apps directories also involves some change to make the dialog Box callable in apps.  
    [Making dialog callable in Writer and Calc](https://gerrit.libreoffice.org/#/c/74598/)  
    [Making dialog callable in Impress and Draw](https://gerrit.libreoffice.org/#/c/77438/)  

    Fix associated with above topic  
    [Right Click the QR code to get edit option](https://gerrit.libreoffice.org/#/c/76957/)    

* Implemented ODF import/export details for our QR code.

    Our QR Code is generated as shape. It is the ODF(Open Document Foundation) code that helps our QR code to retain the property of QR code when save/load.  
    Link to work: [ODF changes](https://gerrit.libreoffice.org/#/c/74853/)  

* Bugzilla Ticket: Fixing label length fix UI break

    [Fix](https://gerrit.libreoffice.org/#/c/77751/) to ticket [tdf#126720](https://bugs.documentfoundation.org/show_bug.cgi?id=126720).   

* Bugzilla Ticket: Help page for QR Code  

    [Fix](https://gerrit.libreoffice.org/#/c/77851/) to ticket [tdf#126721](https://bugs.documentfoundation.org/show_bug.cgi?id=126721). 

## Final Product

Now, QR Code can be generated for any text in the LibreOffice. It is one of the big step that QR Code can be made inside LO now which was only possible using extensions.   

The future development of project include using the QR Code feature in areas like mail-merge, and templates.   
To generate a QR Code image in any of writer, impress, calc or draw.

# Using

Goto   **Insert -> QR Code ..**   

A Dialog Box appers

![](/images/dialog.png)   

**URL** - the text for which the QR will be made   
**Correction** - Select Complexity of QR code.   
**Border** - For a white border around the QR code   

Example QR Code generated from above given inputs

![](/images/qr.png)   

##    Features

1. QR Code is generated at cursor position.
2. QR Code can be generated at selected cell.
3. The QR Code generated is SVG, better rendering and scalablity.
4. We can edit a existing QR code.


# TODO

* Complete the OOXML details for our QR code.
* Extend feature to generate QR code for selected text.

# Others

* [mail-merge: A new project opportunity at LibreOffice][tdf#87195]
* [My LibreOffice GSoC 2019 Journey](/gsoc-2019)
* [LibreOffice GSoC 2019 status reports][status-report]
* [Overall LibreOffice Code Contribution][GSoC-commit]

[nayuki's-library]: https://github.com/nayuki/QR-Code-generator
[tdf#87195]: https://bugs.documentfoundation.org/show_bug.cgi?id=87195
[GSoC-commit]: https://gerrit.libreoffice.org/#/q/shubham+goyal
[status-report]: http://document-foundation-mail-archive.969070.n3.nabble.com/template/NamlServlet.jtp?macro=search_page&node=1621684&query=week+report+shubham+goyal&days=0
