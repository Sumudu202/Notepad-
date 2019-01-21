# Notepad plus plus
## How to 'connect' notepad-plus-plus snap to the wine-platform snap in Ubuntu 16.04?

System info: <br />
~$ snap --version <br /><br />
snap    2.36.3 <br />
snapd   2.36.3 <br />
series  16 <br />
ubuntu  16.04 <br />
kernel  4.13.0-36-generic <br /><br />

$ snap list <br />
Name&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;               Version&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        Rev&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   Tracking&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  Publisher&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   Notes <br />
core&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;               16-2.36.3&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      6130&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  stable&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    canonical✓&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  core <br />
notepad-plus-plus  7.6.2          173   stable    mmtrt       - <br />
wine-platform      3.0.4-4.0~rc7  58    stable    mmtrt       - <br /><br />

Update: <br />
snap interfaces | grep notepad-plus-plus <br />
:cups-control                    notepad-plus-plus <br />
:desktop                         notepad-plus-plus <br />
:desktop-legacy                  notepad-plus-plus <br />
:hardware-observe                notepad-plus-plus <br />
:home                            notepad-plus-plus <br />
:network                         notepad-plus-plus <br />
:opengl                          notepad-plus-plus <br />
:process-control                 notepad-plus-plus <br />
:removable-media                 notepad-plus-plus <br />
:wayland                         notepad-plus-plus <br />
:x11                             notepad-plus-plus <br />
wine-platform:wine-base-stable   notepad-plus-plus:wine-platform-plug <br /><br />

If you don’t see wine-platform in ~$ snap list and/or ~$ snap interfaces | grep notepad-plus-plus, then  <br />
~$ snap install wine-platform <br />
~$ snap connect notepad-plus-plus:wine-platform-plug wine-platform:wine-base-stable <br />
~$ notepad-plus-plus
