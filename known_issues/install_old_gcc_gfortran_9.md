# Install gcc gfortran v9 to compile old codes (e.g., MESH model)
- Install `gcc9-fortran` from the add/remove sfotware GUI (AUR package). **The installation process takes ~3 hours**.
- Verify that the installation was sucessful by running the following in the terminal:
  - `gcc-9 --version`. This should return the following:
    ```
    gcc-9 (Arch Linux 9.5.0-1) 9.5.0
    Copyright (C) 2019 Free Software Foundation, Inc.
    This is free software; see the source for copying conditions.  There is NO
    warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
    ```
  - `gfortran-9 --version`. This should return the following:
    ```
    GNU Fortran (Arch Linux 9.5.0-1) 9.5.0
    Copyright (C) 2019 Free Software Foundation, Inc.
    This is free software; see the source for copying conditions.  There is NO
    warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
    ```
- Build the code by specifying `gcc-9` and `gfortran-9` as parameters to the `make` command as:

  `make CC=gcc-9 FC=gfortran-9`
  
- Alternatively, in the makefile of your code, change all `CC=gcc` and `FC=gfortran` to `CC=gcc-9` and `FC=gfortran-9`. In this case you just run `mkae` without specifying the specific compiler.
