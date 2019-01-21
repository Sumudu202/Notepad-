# Notepad plus plus
How to 'connect' notepad-plus-plus snap to the wine-platform snap in Ubuntu 16.04?

System info: <br />
~$ snap --version <br /><br />
snap    2.36.3 <br />
snapd   2.36.3 <br />
series  16 <br />
ubuntu  16.04 <br />
kernel  4.13.0-36-generic <br /><br />

~$ snap list <br />
Name               Version        Rev   Tracking  Publisher   Notes
core               16-2.36.3      6130  stable    canonical✓  core
notepad-plus-plus  7.6.2          173   stable    mmtrt       -
wine-platform      3.0.4-4.0~rc7  58    stable    mmtrt       -

Update:
snap interfaces | grep notepad-plus-plus
:cups-control                    notepad-plus-plus
:desktop                         notepad-plus-plus
:desktop-legacy                  notepad-plus-plus
:hardware-observe                notepad-plus-plus
:home                            notepad-plus-plus
:network                         notepad-plus-plus
:opengl                          notepad-plus-plus
:process-control                 notepad-plus-plus
:removable-media                 notepad-plus-plus
:wayland                         notepad-plus-plus
:x11                             notepad-plus-plus
wine-platform:wine-base-stable   notepad-plus-plus:wine-platform-plug

If you don’t see wine-platform in ~$ snap list and/or ~$ snap interfaces | grep notepad-plus-plus, then  
~$ snap install wine-platform
~$ snap connect notepad-plus-plus:wine-platform-plug wine-platform:wine-base-stable
~$ notepad-plus-plus
