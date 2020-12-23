my gentoo install, which should be referenced as a supplement to the official handbook: https://wiki.gentoo.org/wiki/Handbook:AMD64/Installation/Bootloader

# portage
- Refer to my make.conf file located in `etc/portage/make.conf` and add USE flags + MAKEOPTS according to your needs.
- Update mirrors, using [mirrorselect](https://wiki.gentoo.org/wiki/Handbook:AMD64/Installation/Base)
- Emerge [rust-bin](https://packages.gentoo.org/packages/dev-lang/rust-bin) before using `emerge --sync` and updating @world
- Install [ccache](https://wiki.gentoo.org/wiki/Ccache)
- I just accept every license in `package.license` because I could care less.

# nvidia & gentoo-kernel-bin
genkernel probably hates me so I just use gentoo-kernel-bin because I have proprietary NVIDIA drivers.

I add `blacklist nouveau` to `/etc/modprobe.d/blacklist.conf` before emerging nvidia-drivers. Refer to https://wiki.gentoo.org/wiki/NVIDIA/nvidia-drivers

# dwm
Check out my repository [here](https://github.com/borsched/dwm). Patches were generated using `git diff`.

My `config.diff` patch uses alacritty, dmenu, slstatus, and additional programs that are binded, which you can find out by reading the source code.

I use patches because I use lightdm. Install dwm after you move the patches. Everything else can be installed normally.

Fonts are from [here](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/Hack). Follow the guide and move the fonts to `/usr/share/fonts/`, run the commands, and reboot.

# xrandr
dwm autostart:

	xrandr --output DP-0 --primary --mode 1920x1080 --rate 165 --output DVI-D-0 --mode 1920x1080 --rate 144 --right-of DP-0 --output HDMI-0 --pos 960x-1080

# dhcpcd
https://wiki.gentoo.org/wiki/Network_management_using_DHCPCD

