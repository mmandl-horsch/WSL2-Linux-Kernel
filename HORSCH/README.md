# Configuring

```bash
make KCONFIG_CONFIG=HORSCH/config-wsl menuconfig
```

# Building

```bash
make -j$(nproc) KCONFIG_CONFIG=HORSCH/config-wsl
```

# Installing

```bash
make INSTALL_MOD_PATH="$PWD/modules" modules_install
sudo ./Microsoft/scripts/gen_modules_vhdx.sh "$PWD/modules" $(make -s kernelrelease) modules.vhdx
```

Copy `arch/x86_64/boot/bzImage` and `modules.vhdx` to a Windows-Accessible location and add it to `C:\Users\USERNAME\.wslconfig`:

```ini
[wsl2]
kernel=C:\\wsl-kernels\\bzImage
kernelModules=C:\\wsl-kernels\\modules.vhdx
```

and restart WSL (`wsl.exe --shutdown`).
