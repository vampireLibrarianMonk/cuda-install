
# CUDA Installation

### 1. Check NVIDIA GPU Compatibility:
Before proceeding, make sure your system has an NVIDIA GPU that supports CUDA. You can check by running:
```bash
lspci | grep -i nvidia
```

### 2. Install NVIDIA Drivers:
First, install the recommended NVIDIA driver for your GPU. Use the following command to install the driver:
```bash
sudo apt install nvidia-driver-<version>
```
Replace `<version>` with the recommended driver version for your system (e.g., `nvidia-driver-535`). Reboot the system once installation is complete.

### 3. Add CUDA Repository Key:
Add the CUDA repository key to your system:
```bash
sudo apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu<version>/x86_64/7fa2af80.pub
```

### 4. Add CUDA Repository:
Add the CUDA repository to your sources list. Replace `<version>` with your Ubuntu version (e.g., `2204` for Ubuntu 22.04):
```bash
sudo sh -c 'echo "deb https://developer.download.nvidia.com/compute/cuda/repos/ubuntu<version>/x86_64/ /" > /etc/apt/sources.list.d/cuda.list'
```

### 5. Update the Package List:
Update your package list to include the new CUDA repository:
```bash
sudo apt update
```

### 6. Install CUDA Toolkit:
Install the CUDA toolkit:
```bash
sudo apt install cuda
```

### 7. Set Environment Variables:
After installation, set up the environment variables by adding the following lines to your `.bashrc` or `.zshrc`:
```bash
export PATH=/usr/local/cuda/bin:$PATH
export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH
```

Then, reload your `.bashrc`:
```bash
source ~/.bashrc
```

### 8. Verify CUDA Installation:
Verify that CUDA is installed by checking its version:
```bash
nvcc --version
```
