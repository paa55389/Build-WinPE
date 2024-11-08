# Build-WinPE
Builds a Custom WinPE and add Optional Components

Builds a new Windows PE (WinPE) and add common Optional Components (OCs) to extend the capabilities of the Windows PE you build.

WinPE Optional Components included;

WinPE Optional Components are available when you install the Windows ADK and are located at this path: C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs

The following is a complete listing of all functionality you can add to WinPE by adding WinPE OCs;

WinPE-DismCmdlets

WinPE-Dot3Svc

WinPE-EnhancedStorage

WinPE-FMAPI

WinPE-Fonts-Legacy

WinPE-FontSupport-JA-JP

WinPE-FontSupport-KO-KR

WinPE-FontSupport-WinRE

WinPE-FontSupport-ZH-CN

WinPE-FontSupport-ZH-HK

WinPE-FontSupport-ZH-TW

WinPE-GamingPeripherals

WinPE-HSP-Driver

WinPE-HTA

WinPE-LegacySetup

WinPE-MDAC

WinPE-NetFx

WinPE-PlatformId

WinPE-PmemCmdlets

WinPE-PowerShell

WinPE-PPPoE

WinPE-RNDIS

WinPE-Scripting

WinPE-SecureBootCmdlets

WinPE-SecureStartup

WinPE-Setup-ASZ

WinPE-Setup-Client

WinPE-Setup-Server

WinPE-Setup

WinPE-StorageWMI

WinPE-WDS-Tools

WinPE-WinReCfg

WinPE-WMI

WinPE-x64-Support

Note: For each WinPE OC, you also need to install its language components, located in the language subfolder for the language you want to provide support for. For example, French language Optional Component support is available from C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\fr-fr. Several of the OCs are font sets and do not have corresponding language components. You would add these, for example, Japanese or Korean font support, to enable Japanese or Korean character sets in WinPE.

More details on WinPE are available on Microsoft.com at this URL: https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/winpe-intro

Getting Started

What can you do with WinPE? A lot... but according to Microsoft, it is intended to be used to install Windows onto devices and for use with Windows Recovery.

Before you can build and customize a WinPE, you need to install the Windows ADK onto your Technician PC

Requirements

Install the Windows ADK on your Technician PC. If you do not already have the latest Windows ADK installed (including the Windows PE add-on), you can download it from Microsoft at this link: https://docs.microsoft.com/en-us/windows-hardware/get-started/adk-install

Build WinPE

After you have installed the Windows ADK on your Technician PC, launch the Deployment and Imaging Tools Environment (the Command Line Interface (CLI)for the Windows ADK) and run one of the following commands to create a new WinPE;

32-bit WinPE

copype x86 c:\WinPE\x86

64-bit

copype amd64 c:\WinPE\x64

The new WinPE will be created and is ready for use. However, it's functionality may not support some of the actions you require. If you need WinPE to support more advanced functionality, you need to add that functionality before it can be supported in WinPE. You do this by adding WinPE Optional Components, or OCs, as shown in the examples below.

For more details on building and customizing WinPE, see this Microsoft website: https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/winpe-mount-and-customize

Extend the capabilities of the WinPE by adding WinPE Optional Components (OCs) using DISM

In this example, the following list of OCs are added. These are common OCs, but your requirements might mean you need other OCs. The method to add them is the same - Add the core OC, then add the language component.

Scripting

WMI

.Net Framework

HTA

PowerShell

DISM Commandlets
Scripting OC and its English language component

dism /image:"c:\mount\winpe" /add-package /packagepath:"c:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\WinPE-Scripting_en-us.cab"

dism /image:"c:\mount\winpe" /add-package /packagepath:"c:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\en-us\WinPE-Scripting_en-us.cab"

WMI OC and its English language component

dism /image:"c:\mount\winpe" /add-package /packagepath:"c:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\WinPE-WMI.cab"


dism /image:"c:\mount\winpe" /add-package /packagepath:"c:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\en-us\WinPE-WMI_en-us.cab"

DotNet Framework and its English language component

dism /image:"c:\mount\winpe" /add-package /packagepath:"c:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\WinPE-NetFx.cab"

dism /image:"c:\mount\winpe" /add-package /packagepath:"c:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\en-us\WinPE-NetFx_en-us.cab"

HTML Application (HTA) support and its English language component

dism /image:"c:\Mount\WinPE" /add-package /packagepath:"c:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\WinPE-HTA.cab"

dism /image:"c:\Mount\WinPE" /add-package /packagepath:"c:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\en-us\WinPE-HTA_en-us.cab"

PowerShell and its English language component

dism /image:"c:\Mount\WinPE" /add-package /packagepath:"c:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\WinPE-PowerShell.cab"

dism /image:"c:\Mount\WinPE" /add-package /packagepath:"c:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\en-us\WinPE-PowerShell_en-us.cab"

DISM Commandlets and its English language component

dism /image:"c:\Mount\WinPE" /add-package /packagepath:"c:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\WinPE-DismCmdlets.cab"

dism /image:"c:\Mount\WinPE" /add-package /packagepath:"c:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\en-us\WinPE-DismCmdlets_en-us.cab"

After you have created and customized WinPE, you can create bootable media, or load the WinPE into WDS

Create a Bootable ISO

Often it is useful to perform tests using virtual PCs. To create a bootable WinPE for use with a virtual machine (VM), it is easiest to attach an ISO file to the VM. Some vendor software allows attaching USB devices, but most do not and for this, you should use a ISO file.

To generate a bootable ISO file, enter the following command into the Deployment and Imaging Tools Environment CLI;

makewinpemedia /iso C:\WinPE_amd64 C:\WinPE_amd64\WinPE_amd64.iso

The above command will create a 64-bit WinPE ISO file named x64.iso. You can modify the path or file name as needed.

The 32-bit command is similar, as follows;

makewinpemedia /iso C:\WinPE_x86 C:\WinPE_x86\WinPE_x86.iso

Create a Bootable USB
To create a bootable WinPE on USB, enter the following command into the Deployment and Imaging Tools Environment CLI;

64-bit version;

makewinpemedia /ufd C:\WinPE_x64 F:

32-bit version;

makewinpemedia /ufd C:\WinPE_x86 F:

Note: The above commands will format and erase the USB F drive (your USB drive letter may be different) and install WinPE. You may need to modify the path as needed.

Add WinPE to Windows Deployment Services (WDS)

An alternative method to boot to WinPE is accomplished by adding the boot.wim file to WDS. If you look inside the Media/Sources subfolders of any WinPE you create, you will find a boot.wim file. This is the WinPE image and it can be added to WDS directly. To do so, simply open the WDS console and select the Boot Images node and right-click, selecting the option to add a Boot Image. Follow the wizard to name the Boot Image and then you can boot to the WinPE over the network.

For more information, see this Microsoft site.

Additional Related Resources

Desktop manufacturing https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/

Windows PE https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/winpe-intro

MakeWinPEMedia Command-Line Options https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/makewinpemedia-command-line-options

Windows 11 DISM Command-Line Options https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/deployment-image-servicing-and-management--dism--command-line-options

Windows Commands https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands

Windows Deployment Services https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj648426(v=ws.11)
