automator-pdf-evernote
======================

This set of automator scripts have been created to easy the automation of organizing PDFs into [Evernote] (http://www.evernote.com)A

| Script                          | Description                                                                 |
| ------------------------------- | --------------------------------------------------------------------------- |
| PDF to Evernote.workflow        | Image Capture script to import scans directly into Evernote as a PFD        |
| Secure PDF to Evernote.app      | Auotmator app that takes a PDF and encrypts it and imports into Evernote    |
| Secure PDF to Evernote.workflow | Image Capture script to import scans directly into Evernote as a Secure PDF |



Update {"Local Inbox"} to the name of the Evernote notebook you which to import PDFs into

    on run {input, parameters}
        tell application id "com.evernote.evernote"
            activate
            create note from file input notebook {"Local Inbox"}
        end tell
    end run


To encrypt PDFs, set the password with Auotmator.app and save


