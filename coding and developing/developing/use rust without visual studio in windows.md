for a lightweight rust setup. use GNU compiler instead

### step 1: install the GNU compiler collection (gcc) via MSYS2
- download and install [MSYS2](https://www.msys2.org/)
- open the **MSYS2 MinGW 64-bit** terminal (make sure it's the **MinGW 64** version, not the default MSYS one)
- run the following command to install the required C/C++ toolchain
```
pacman -S --needed base-devel mingw-w64-x86_64-toolchain
```
### step 2: add MSYS2 to System PATH
- open the Windows Start Menu, search for **"Edit the system environment variables"**, and open it.
- select **Path** then click edit to add the path
- click new then add the path to mingw64\bin folder
	- example: `C:\msys64\mingw64\bin`
- click ok to save
### step 3: install Rust and configure the GNU toolchain
- download and install [rust](https://rust-lang.org/tools/install/)
	when run the installer, a terminal should open with few option
- choose `2) customize installation`
- when it asks for the **Default host triple**, type: `x86_64-pc-windows-gnu`
- press enter and keep configuring then proceed the installation
### verify installation
```
cargo --version
rustc --version
```

---
#developing 