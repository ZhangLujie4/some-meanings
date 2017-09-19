# win7和ubuntu16双系统的win7开机花屏问题的解决方法

遇到此类情况，如果win7系统花屏进不去，打开ubuntu终端输入：
 `sudo grub-install /dev/sda`
 `sudo chmod -x /etc/grub.d/30_os-prober`
 `sudo gedit /etc/grub.d/40_custom`
 
 贴入以下内容：
 `menuentry "Windows 7" {
 set root=(hd0,1)
 ntldr /bootmgr
 boot
 }
 `
 最后在终端输入：
 `sudo update-grub`

