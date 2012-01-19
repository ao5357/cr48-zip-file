# File ZIPper

This is the working repo for a Google Chrome extension (using chrome.fileBrowserHandler for chromeos only) that will allow a user to select files/folders from the file manager and compress them together into a ZIP file.

One goal of this project is for it to be developed entirely on Cr-48s or other Chromebooks.

The distribution version of this extension will be hosted in the Chrome Web Store, so this repo is only for development. Issues, forks, and pull requests welcome!

File ZIPper for Chrome OS is licensed under the [Apache Licence,
Version 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).

##Progress reports
###18 Jan 2012, 10:46PM
I figured out how, on my Cr-48, to get images into a git repo on Cloud9 IDE. Since Chrome OS doesn't have drag and drop functionality from the file browser to other tabs (or from anywhere to anywhere else for that matter!), it's necessary to use a conventional or flash file upload form element.

cloud9 uses HTML5 drag and drop exclusively, so that's a no-go. GitHub lets you upload files, but not into repos; they're just download packages and so forth. A third tool is necessary to bring this together. In my case I used [eXo Cloud IDE](http://www.cloud-ide.com/).

After the registration process, the home screen makes it easy to clone an existing GitHub repo into eXo. Once loaded, select "Upload File" from the file menu. Select the file from the manager, then type in the intended MIME type into the text field below.

Once you've uploaded all the files, add them from the git menu, then subsequently commit them. Finally, open the remotes sub-menu and click the remotes item. Delete origin and create a new origin remote with the GitHub-provided ssh address. From the window menu select "ssh key manager" and press the "generate key" button. Put in github.com as the hostname; it'll make a key which you can then view and copy. Paste it into your GitHub account's ssh key section in account settings. Finally, from the git menu -> remotes sub-menu, push the appropriate branch to the appropriate remote.

This cumbersome process is necessary for fully developing a chrome extension, and is currently one of very few methods to do so on a chromebook.