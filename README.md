automator-pdf-evernote
======================

This set of [Automator](<http://en.wikipedia.org/wiki/Automator_(software)>) scripts for [Mac](http://www.mac.com) have been created to automate the organization of PDFs into [Evernote](http://www.evernote.com) and assist in living a [paperless](http://lifehacker.com/tag/paperless) life.

### Automator Scripts

| Script                          | Description                                                                 |
| ------------------------------- | --------------------------------------------------------------------------- |
| PDF to Evernote.workflow        | Image Capture plugin to import scans directly into Evernote as a PFD        |
| Secure PDF to Evernote.workflow | Image Capture plugin to import scans directly into Evernote as a Secure PDF |
| Secure PDF to Evernote.app      | Auotmator app that takes a PDF and encrypts it and imports into Evernote    |

### Installation

1. Move Secure PDF to Evernote.app to Applications or your Desktop
2. Double click on PDF to Evernote.workflow & Secure PDF to Evernote.workflow to install them as Image Capture plugins

### Set Import Notebook

Update {"Local Inbox"} to the name of the Evernote notebook you which to import PDFs into

    on run {input, parameters}
        tell application id "com.evernote.evernote"
            activate
            create note from file input notebook {"Local Inbox"}
        end tell
    end run


### Encryption Password

To encrypt PDFs, set the password with Auotmator.app and save


### Secure Delete

Once a PDF is import the file will be securely via [srm] (https://developer.apple.com/library/mac/documentation/Darwin/Reference/ManPages/man1/srm.1.html)

    for i in "$@"
    do
      srm -rsf "$i"
    done



