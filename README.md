scan-to-evernote
======================

This set of [Automator][1] scripts for [Mac](http://www.mac.com) has been created to automate the organization of PDFs into [Evernote](http://www.evernote.com) and assist in living a [paperless](http://lifehacker.com/tag/paperless) life.

### Automator Scripts

| Script                          | Description                                                                    |
| ------------------------------- | -------------------------------------------------------------------------------|
| PDF to Evernote.workflow        | Image Capture plugin to import scans directly into Evernote as a PDF           |
| Secure PDF to Evernote.workflow | Image Capture plugin to import scans directly into Evernote as a Secure PDF    |
| Secure PDF to Evernote.app      | *Bonus* Automator app that takes a PDF, encrypts it, and imports into Evernote |

### Installation

#### 1) Set Import Notebook

1. Open the scripts with Automator.app
2. Update {"Local Inbox"} to the name of the Evernote notebook you which to import PDFs into and save


    on run {input, parameters}
        tell application id "com.evernote.evernote"
            activate
            create note from file input notebook {"Local Inbox"}
        end tell
    end run



#### 2) Set Encryption Password

1. Open the scripts with Automator.app
1. Set the password and save

#### 3) Install

1. Move Secure PDF to Evernote.app to Applications or your Desktop
2. Double click on PDF to Evernote.workflow & Secure PDF to Evernote.workflow to install them as Image Capture plugins


### How To Use

#### Image Capture Plugins

1. Open Image Capture.app
2. In the "Format" field, select "PDF" Format
3. In the "Scan To" field, select "PDF to Evernote" or "Secure PDF to Evernote"
4. Click "Scan"

##### Secure PDF to Evernote App

1. Drag PDF document to Secure PDF to Evernote.app

### Secure Delete

Once a PDF is imported the file will be securely deleted via [srm] (https://developer.apple.com/library/mac/documentation/Darwin/Reference/ManPages/man1/srm.1.html)

    for i in "$@"
    do
      srm -rsf "$i"
    done


[1]: http://en.wikipedia.org/wiki/Automator_(software)
