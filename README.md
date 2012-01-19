# File ZIPper

This is the working repo for a Google Chrome extension (using chrome.fileBrowserHandler for chromeos only) that will allow a user to select files/folders from the file manager and compress them together into a ZIP file.

One goal of this project is for it to be developed entirely on Cr-48s or other Chromebooks.

The distribution version of this extension will be hosted in the Chrome Web Store, so this repo is only for development. Issues, forks, and pull requests welcome!

File ZIPper for Chrome OS is licensed under the [Apache Licence,
Version 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).

##Progress reports
I've decided to document the dev process and put it here. These reports will focus on setup, workflow, and especially bugs and gotchas. Hopefully it will be useful to someone searching google for something obscure.
###18 Jan 2012, 8:00-ish
I decided I want to try my hand at writing another chrome extensionl; this time entirely on my chromebook. I've toyed around with many browser-based IDEs: kodingen, codeita, flavors of bespin, etc. Cloud9 came with glowing recommendations and GitHub integration, so that was a no-brainer.

Once I made the git-based project and gave it a name, I created a manifest file and pasted in some stuff from the extension API docs.

The Cloud9 console is pretty cool. You can do all the normal git stuff down there. Use the -m flag for your commit messages or else it'll yell at you.

One way this process is funky is that you have to use Cloud9 to initiate the GitHub repo. You don't NEED a GitHub repo to create an extension, I suppose (see the image thing from three hours later, though), but if nothing else it's a backup solution. To set it up just follow the instructions that appear when you press the "New Repository" button on your GitHub profile page. You can't set global configs, so just skip to the adding a remote, adding files, commiting, and pushing parts.

Your Cloud9 ssh key can be found on the Dashboard on the "Your Account" screen on the right-hand side. Copy the key and paste it into your keys in your GitHub account settings. This will allow you to push from the web app. Give it a go in the Cloud9 console! "git push -u remote origin"

###18 Jan 2012, 10:46PM
I figured out how, on my Cr-48, to get images into a git repo on Cloud9 IDE. Since Chrome OS doesn't have drag and drop functionality from the file browser to other tabs (or from anywhere to anywhere else for that matter!), it's necessary to use a conventional or flash file upload form element.

cloud9 uses HTML5 drag and drop exclusively, so that's a no-go. GitHub lets you upload files, but not into repos; they're just download packages and so forth. A third tool is necessary to bring this together. In my case I used [eXo Cloud IDE](http://www.cloud-ide.com/).

After the registration process, the home screen makes it easy to clone an existing GitHub repo into eXo. Once loaded, select "Upload File" from the file menu. Select the file from the manager, then type in the intended MIME type into the text field below.

Once you've uploaded all the files, add them from the git menu, then subsequently commit them. Finally, open the remotes sub-menu and click the remotes item. Delete origin and create a new origin remote with the GitHub-provided ssh address. From the window menu select "ssh key manager" and press the "generate key" button. Put in github.com as the hostname; it'll make a key which you can then view and copy. Paste it into your GitHub account's ssh key section in account settings. Finally, from the git menu -> remotes sub-menu, push the appropriate branch to the appropriate remote.

This cumbersome process is necessary for fully developing a chrome extension, and is currently one of very few methods to do so on a chromebook.