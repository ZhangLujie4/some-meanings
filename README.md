# win7和ubuntu16双系统的win7开机花屏问题的解决方法

遇到此类情况，如果win7系统花屏进不去，打开ubuntu终端输入：<br />
 `sudo grub-install /dev/sda`<br />
 `sudo chmod -x /etc/grub.d/30_os-prober`<br />
 `sudo gedit /etc/grub.d/40_custom`<br />
 
 贴入以下内容：<br />
 `menuentry "Windows 7" {<br />
 set root=(hd0,1)<br />
 ntldr /bootmgr<br />
 boot<br />
 }<br />
 `
 最后在终端输入：<br />
 `sudo update-grub`<br />

