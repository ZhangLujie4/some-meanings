# win7和ubuntu16双系统的win7开机花屏问题的解决方法
`ps:基本以下两种情况会同时遇到`

## 遇到此类情况，如果win7系统花屏进不去
打开ubuntu终端输入：<br />
 `sudo grub-install /dev/sda`<br />
 `sudo chmod -x /etc/grub.d/30_os-prober`<br />
 `sudo gedit /etc/grub.d/40_custom`<br />
 
 贴入以下内容：<br />
 `menuentry "Windows 7" {`<br />
 `set root=(hd0,1)`<br />
 `ntldr /bootmgr`<br />
 `boot`<br />
 `}`<br />
 最后在终端输入：<br />
 `sudo update-grub`<---(不要忘记)<br />

## 如果win7系统偶尔花屏,但重启几次恢复
打开ubuntu终端输入：<br />
`sudo gedit /etc/default/grub`<br />

* 取消注释 `GRUB_TERMINAL = console`<br />
* 修改 `GRUB_CMDLINE_DEFAULT = "quiet splash"` 为 `GRUB_CMDLINE_DEFAULT = "quiet splash nomodest"`<br />

 最后在终端输入：<br />
 `sudo update-grub`<---(不要忘记)<br />



