# Building

```bash
make -j$(nproc) KCONFIG_CONFIG=HORSCH/config-wsl
```

# Installing

```bash
sudo make modules_install headers_install
```

Copy `arch/x86_64/boot/bzImage` to a Windows-Accessible location and add it to `C:\Users\USERNAME\.wslconfig`:

```ini
[wsl2]
kernel=C:\\wsl-kernels\\bzImage
```

and restart WSL (`wsl.exe --shutdown`).
