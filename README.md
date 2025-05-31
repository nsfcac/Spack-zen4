# Spack environment for the zen4 partition of REPACSS
This repository tracks the packages installed via Spack for the `zen4` partition of the REPACSS cluster. If you wish to test or contribute new packages, please follow the instructions below.

## Using a Local Spack Install Tree (For Testing)
To test and install packages in your own user environment without affecting the shared installation:

1. Clone the reporsitory:
```bash
git clone https://github.com/nsfcac/Spack-zen4.git
cd Spack-zen4
```

2. Enable local install tree:
Uncomment the following lines in spack.yaml to use a custom install location:
```yaml
config:
  install_tree: $HOME/.spack/.spack-store
```

3. Activate the environment:
```bash
spack env activate . -p
```
>The `-p` flag updates your shell prompt to show the active environment (e.g., `[Spack-zen4]`).

4. Test and install packages in your personal environment without interfering with system-wide configurations.

## Finding and Installing a Package
Follow these steps to search for and install a package:

1. Search for a package (e.g., for MPI libraries):
```bash
spack list mpi
```

2. Get detailed info about a package (e.g., available versions, variants, and dependencies):
```bash
spack info mpich
```

3. Add a package to the environment (example with a specific version):
```bash
spack add mpich@4.2.3
```
4.	Concretize and install:
```bash
spack concretize
spack install
```

## Notes

- Only modify spack.yaml when making changes for the shared environment.
-	Use a separate branch or fork for proposing changes, and submit a pull request when ready.