# Openfhe-rs Template Project

This repository contains all you need to create an FHE-enabled application using [openfhe](https://crates.io/crates/openfhe) rust crate.

# Getting started

To build the code in this repositorym, you need to install the `OpenFHE` core library on your system. That will provide you with low-level optimizations.

## Install dependencies
    
* CMake >= 3.5.1
* Clang >= 12.0 or GCC >= 11.4
* Rust >= 1.78
* Git

### Unix

On Debian systems, everything can be installed with the following command:

```bash
sudo apt install build-essential libssl-dev cmake clang git
```

## Installation process

### Core OpenFHE library installation

Build and install OpenFHE library. Right now you need to use the Fair Math fork. It contains the required features, which will be included in the next planned release (v1.1.5):

1. Clone the repository

```bash
git clone https://github.com/fairmath/openfhe.git
cd openfhe
```

2. Configure CMake

```bash
cmake -B ${OPENFHE_BUILD:-build} -DBUILD_EXAMPLES=ON -DBUILD_EXTRAS=ON -DBUILD_SHARED=ON .       
```

3. Build and install the C++ OpenFHE library

```bash
make -C ${OPENFHE_BUILD:-build} -j$(nproc)
make -C ${OPENFHE_BUILD:-build} install
```

4. Configure your dynamic linker

```bash
sudo ldconfig
```
