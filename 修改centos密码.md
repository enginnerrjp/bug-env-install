1. 启动系统，在GRUB2引导画面，按E键，编辑引导项 
2. 删除linux16这一行最后的 rhgb和 quiet参数（在UEFI系统中是linuxefi），删除rhgb和quiet这两个参数是为了显示系统信息 
3. 添加以下参数：rd.break enforcing=0 
在64位IBM Power Series是linux这一行尾；在x86-64 BIOS引导的系统中是linux16这一行尾；在UEFI引导的系统中是linuxefi这一行尾 
4. ctrl+X 改变参数引导系统
5. 在/sysroot/文件系统被挂载为只读时，你不能改变密码，因为文件系统为不可写入。重新挂载文件系统为可写入。 
mount -o remount,rw /sysroot

6. 文件系统被重新挂载为可写，像下面这样改变文件系统的root 
chroot /sysroot

7. 输入passwd命令，接下来命令行提示改变root密码
8. 更新password文件会导致SELinux安全上下文文件错误。键入以下命令在下次系统引导前重新标记所有文件： touch /.autorelabel

9. 重新挂载系统为只读： mount -o remount,ro / 
10. 键入exit命令退出chroot环境： exit

11. 再次键入exit命令完成初始化，完成系统引导。 exit 
