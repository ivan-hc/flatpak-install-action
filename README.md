# flatpak-install-action
A custom action to install applications from flathub by pressing the "install" button in Firefox via bash.

# Setup
1. place the *.desktop file in ~/.local/share/applications

       mkdir -p ~/.local/share/applications && wget https://raw.githubusercontent.com/ivan-hc/flatpak-install-action/main/Flathub%20Install%20Action.desktop -O ~/.local/share/applications/'Flathub Install Action.desktop' && chmod a+x ~/.local/share/applications/'Flathub Install Action.desktop'
2. place the flatpak.svg icon in ~/.local/share/icons

       mkdir -p ~/.local/share/icons/ && wget https://raw.githubusercontent.com/ivan-hc/flatpak-install-action/main/flatpak.svg -O ~/.local/share/icons/flatpak.svg
3. open the ~/.mozilla/firefox/$YOUR-PROFILE/handlers.json file with a text editor and add the following line after `"mimeTypes":{`

       "application/vnd.flatpakref":{"action":4,"ask":true,"extensions":["flatpak"]},
   it should look like this
   
       ..."mimeTypes":{"application/vnd.flatpakref":{"action":4,"ask":true,"extensions":["flatpak"]},...
4. Right-click on the downloaded .flatpakref file (only the first time) to enable Flatpak Install Action as the default app for this extension.       

5. Go to https://flathub.org and click the "Install" button of an app you're interested in and select "Flathub Install Action" to open the file into a Terminal's window. The terminal will be automatically closed at the end of the installation or if you choose "n" to abort the installation.
