# M1 QEMU VM

## How to

```bash
brew install ihsakashi/qemu/qemu ihsakashi/qemu/libvirt

echo 'security_driver = "none"' >> /opt/homebrew/etc/libvirt/qemu.conf
echo "dynamic_ownership = 0" >> /opt/homebrew/etc/libvirt/qemu.conf
echo "remember_owner = 0" >> /opt/homebrew/etc/libvirt/qemu.conf

ln -s /opt/homebrew/Cellar/qemu/_VERSION_/share/qemu /opt/homebrew/Cellar/libvirt/_VERSION_/share/qemu

brew services start libvirt
```

Then, create a configuration based off mine and rely on `virsh`.

## Bugs

 * Can't mount disks without sudo.
 * Network interface doesn't work. QEMU seems to be patched for it though.
 * CDROM type drive doesn't work. UEFI firmware seems to rejects it.

