#!/usr/bin/awk -f
function show(x, y)
{
	color1 = "\033[0;33m"
	color2 = "\033[1;37m"
	printf "\t%s%-23s %s%s\n", color1, x, color2, y
}

BEGIN {
	print "\
[38;5;208m                                           .\n\
[38;5;208m     .vir.                                d$b\n\
[38;5;208m  .d$$$$$$b.    .cd$$b.     .d$$b.   d$$$$$$$$$$$b  .d$$b.      .d$$b.\n\
[38;5;208m  $$$$( )$$$b d$$$()$$$.   d$$$$$$$b Q$$$$$$$P$$$P.$$$$$$$b.  .$$$$$$$b.\n\
[38;5;208m  Q$$$$$$$$$$B$$$$$$$$P\"  d$$$PQ$$$$b.   $$$$.   .$$$P' `$$$ .$$$P' `$$$\n\
[38;5;208m    \"$$$$$$$P Q$$$$$$$b  d$$$P   Q$$$$b  $$$$b   $$$$b..d$$$ $$$$b..d$$$\n\
[38;5;208m   d$$$$$$P\"   \"$$$$$$$$ Q$$$     Q$$$$  $$$$$   `Q$$$$$$$P  `Q$$$$$$$P\n\
[38;5;208m  $$$$$$$P       `\"\"\"\"\"   \"\"        \"\"   Q$$$P     \"Q$$$P\"     \"Q$$$P\"\n\
[38;5;208m  `Q$$P\"                                  \"\"\"\n\
[38;5;208m\n"

	getline distro < "/etc/gentoo-release"
	"uname -rvm" | getline kernel
	wm = "awesome"
	term = ENVIRON["TERM"]
	shell = ENVIRON["SHELL"]

	FS="\""
	while (getline < (ENVIRON["HOME"] "/.gtkrc-2.0"))
		switch($0) {
		case /gtk-theme-name/:
			gtk = $2; break
		case /icon-theme-name/:
			icon = $2; break
		case /font-name/:
			font = $2
		}

	show("Distro", "Gentoo Linux (" distro ")")
	show("Kernel", kernel)
	show("Window manager", wm)
	show("Terminal", term)
	show("Shell", shell)
	#show("GTK theme", gtk)
	#show("Icons", icon)
	show("Font", font)
	print ""
}
