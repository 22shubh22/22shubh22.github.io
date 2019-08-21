---
layout: post
title: GSoC'19 LibreOffice - QR Code Generation Final Report
---

# Describe my work briefly

* Integrate a QR Code generating Library.
* Provide a platform to generate QR Code in LibreOffice apps.

# What code got merged.

* Integrated the QR generating Library.
    
    An [external Library][nayuki's-library] was shipped with LibreOffice.  
    Link to work: [bundle external](https://gerrit.libreoffice.org/#/c/73302/)  

* Implemented a QR Code Dialog Box that would be called in LO apps.

    The Dialog Box takes the inputs needed for generating the QR Code.  
    Link to work: [QR Dialog Box](https://gerrit.libreoffice.org/#/c/74167/)  

    Fix associated with above patch  
    [Add qrcodegen ui file to make file](https://gerrit.libreoffice.org/#/c/76376/)
    [Make generated QR Code as a perfect square](https://gerrit.libreoffice.org/#/c/76954/)   
    [Fix Border feature QR Code](https://gerrit.libreoffice.org/#/c/76953/)  
    [Error Correction in QR Code](https://gerrit.libreoffice.org/#/c/76958/)    

* Made QR code Dialog Box callable in LO apps.

    The apps directory also involves some change to make the dialog Box callable in apps.  
    [Making dialog callable in Writer and Calc](https://gerrit.libreoffice.org/#/c/74598/)  
    [Making dialog callable in Impress and Draw](https://gerrit.libreoffice.org/#/c/77438/)  

    Fix associated with above patch  
    [Right Click the QR code to get edit option](https://gerrit.libreoffice.org/#/c/76957/)    

# Code which didn't got merged.

* Implemented ODF import/export details for our QR code.

    Our QR Code is generated as shape. It is the ODF(Open Document Foundation) code that helps our QR code to retain the property of QR code when save/load.  
    Link to work: [ODF changes](https://gerrit.libreoffice.org/#/c/74853/)  

* Bugzilla Ticket: Fixing label length fix UI break

    [Fix](https://gerrit.libreoffice.org/#/c/77751/) to ticket [tdf#126720](https://bugs.documentfoundation.org/show_bug.cgi?id=126720).   

* Bugzilla Ticket: Help page for QR Code  

    [Fix](https://gerrit.libreoffice.org/#/c/77851/) to ticket [tdf#126721](https://bugs.documentfoundation.org/show_bug.cgi?id=126721). 

# Final Product - FIX

images and Extra..

# TODO

* Complete the OOXML details for our QR code.
* Extend feature to generate QR code for selected text.

# Others

* [mail-merge: A new project opportunity in LibreOffice.][tdf#87195]
* [My LibreOffice GSoC 2019 Journey](/gsoc-2019)
* [LibreOffice GSoC 2019 status report - **FIX**][status-report]
* [Overall LibreOffice Code Contribution][GSoC-commit]

[nayuki's-library]: https://github.com/nayuki/QR-Code-generator
[tdf#87195]: https://bugs.documentfoundation.org/show_bug.cgi?id=87195
[GSoC-commit]: https://gerrit.libreoffice.org/#/q/shubham+goyal
[status-report]: http://document-foundation-mail-archive.969070.n3.nabble.com/template/NamlServlet.jtp?macro=search_page&node=1621684&query=week+report+shubham+goyal&days=0