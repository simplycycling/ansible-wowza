# ansible-wowza
## Wowza role for Ansible
This role automates the installation of the Wowza Media Server, including their installer, which contains a very
long EULA, and 5 interactive prompts.

# Requirements
- Java jdk - I use Oracle Java 7, but openjdk will be just fine.
- Wowza license - this you will get when you sign up for a free trial, or you can request a developer license.
- Wowza binary - the Wowza binary (4.7.5) is now wgetted as part of this role.

# Distros tested
Currently, this is only tested on Ubuntu 14.04, but as time allows

## Wait a minute, what the hell is Wowza?
From the Wowza site:

_Wowza Streaming Engine™ is robust, customizable media server software that powers reliable streaming of high-quality video and audio to any device, anywhere._

_Wowza software is platform-agnostic, multi-format, and multi-screen. It takes in any video format, transcodes it once, and reliably delivers it in multiple formats and with the highest possible quality_

## Usage

Wowza needs several user actions on the interactive prompt portion of the installer:
- an acknowledgement of acceptance of their terms
- an administrative user added for using the Wowza console
- a password for the administrative user
- confirmation of that password
- Wowza license key
- an acknowledgement of whether or not you want Wowza to start at boot

Fill these values in, in vars/main.yml. I've already taken the liberty of answering "yes" for the acceptance of terms,
and whether or not you want Wowza to start at boot, but you can easily change that, should you feel the need. Those
values can be edited in the template/script.exp.j2 file.
