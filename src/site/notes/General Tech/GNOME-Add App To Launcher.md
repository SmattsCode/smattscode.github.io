---
{"dg-publish":true,"permalink":"/general-tech/gnome-add-app-to-launcher/","tags":["Type/CodeSnippet","Tech","Tech/Linux","Tech/Linux/Gnome"],"updated":"2026-04-29T15:59:52.649+01:00","dg-note-properties":{"tags":["Type/CodeSnippet","Tech","Tech/Linux","Tech/Linux/Gnome"]}}
---


#  How to Add an Application to the Ubuntu Launcher
Start by copying one of the other `*.desktop` files inside the `/usr/share/applications/` directory.
Give it the name `<YOUR_APP>.desktop`
Then open it up and edit the following lines as shown:

```
Name=<YOUR APP>`
GenericName=<YOUR APP>
Comment=<COMMENT ABOUT YOUR APP>
Exec=</PATH/TO/YOURAPPS/EXECUTABLE>
Icon=</PATH/TO/YOURAPPS/ICON.png>
Terminal=<true/false>
Type=Application
Categories=Utility;
StartupNotify=<true/false>
```
