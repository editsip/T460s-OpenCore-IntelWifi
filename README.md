# ThinkPad T460s with OpenCore & Experimental Intel WiFi

***

### Latest working macOS: 10.15.6 (Big Sur support coming soon!)

**Using OpenCore 0.5.9!**

***


## Introduction

This will allow you to install and use macOS + OpenCore on any T460s model, with native [Intel Wireless and Bluetooth](https://github.com/OpenIntelWireless) support. Please note that this is experimental and still under development, so **it may be unstable or outright not working.**
Repo is updated regularly and I plan on mantaining it for a long time. 

If you're new to this I suggest reading [Dortania's](https://dortania.github.io) guide on how to install macOS. This OC configuration may work for you but you'd be better off learning how it works and rebuilding your configuration & SSDTs. 

Thanks to [acidanthera](https://github.com/acidanthera) for OpenCore, [mszturc](https://github.com/MSzturc) for ThinkPad keyboard patches and [OpenIntelWireless](https://github.com/OpenIntelWireless) for Intel BT+Wifi implementation on macOS. 

Grazie a [simprecicchiani](https://github.com/simprecicchiani) for being the first to build a complete OC configuration for T460s.



## Cut to the chase

**MAKE SURE YOUR LENOVO BIOS IS UPDATED TO THE LATEST VERSION.** If it is not, flash *biosupdate.img* on a thumb drive and update.

Copy the EFI folder in the EFI partition of your booting drive.
Check your BIOS settings:

* `Config` > `USB` > `UEFI BIOS Support` > **Enable**
* `Config` > `Power` > `Intel SpeedStep Technology` > **Enable**
* `Config` > `Power` > `CPU Power Management` > **Enable**
* `Security` > `Security Chip` > **Disable**
* `Security` > `Virtualization` > `Intel Virtualization Technology` > **Disable** (can be enabled later)
* `Security` > `Virtualization` > `Intel VT-d Feature` > **Disable** (can be enabled later)
* `Security` > `Anti-Theft` > `Computrace` > `Current Setting` > **Disable**
* `Security` > `Secure Boot` > **Disable**
* `Security` > `Intel SGX` > **Disable**
* `Security` > `Device Guard` > **Disable**

Power Management is natively supported on i5 and i7 models. Use CPUFriend & CPUFriendFriend to finetune.


### Post-install

It is mandatory to install [HeliPort](https://github.com/OpenIntelWireless) to make Intel Wireless work. It is included in the repo and updated regularly, but you can build your own kext and app from the original repository (recommended)

SMBIOS should be fine for any laptop but I **STRONGLY** recommend to generate a new Serial Number and UUID to use Apple services. [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) does this.

I also suggest [enabling HiDPI support](https://github.com/xzhih/one-key-hidpi) on 1080p and 1440p screens. **hidpi.command** already included in the repo.

**Airdrop & Handoff are not supported yet.**


## Notes

*I'm using a T460s with macOS as a daily driver so this repo will be updated along with OpenIntelWireless & every macOS update. You shouldn't use macOS on a production machine (I do it though. It works good). 
Risks include data loss, bricking the system, losing hair and temper, starting a war, discovering life's true meaning, etc.*

Wireless WAN & Fingerprint Reader are not supported. 
