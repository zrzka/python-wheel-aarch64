# Jetson Nano Wheels

Prebuilt Python packages for Jetson Nano.

## Build Steps

* Download [NVIDIA SDK Manager](https://developer.nvidia.com/embedded/jetpack) (JetPack **4.2**)
  * You have to use Ubuntu for example & VMware Fusion if you're on macOS
* Run the SDK manager, sign in and download all required packages for the Jetson Nano
  * Files will be stored in the `~/Downloads/nvidia/sdkm_downloads` folder
* Run `./prepare.sh` script
  * Creates the `nvidia` folder with all required files
  * Removes the `.gitignore` file otherwise `balena push` will ignore the `nvidia` folder

This is how the `nvidia` folder should look like:

```text
nvidia/
├── config.tbz2
├── deb
│   ├── cuda-repo-l4t-10-0-local-10.0.166_1.0-1_arm64.deb
│   ├── graphsurgeon-tf_5.0.6-1+cuda10.0_arm64.deb
│   ├── libcudnn7-dev_7.3.1.28-1+cuda10.0_arm64.deb
│   ├── libcudnn7-doc_7.3.1.28-1+cuda10.0_arm64.deb
│   ├── libcudnn7_7.3.1.28-1+cuda10.0_arm64.deb
│   ├── libnvinfer-dev_5.0.6-1+cuda10.0_arm64.deb
│   ├── libnvinfer-samples_5.0.6-1+cuda10.0_all.deb
│   ├── libnvinfer5_5.0.6-1+cuda10.0_arm64.deb
│   ├── libopencv-dev_3.3.1-2-g31ccdfe11_arm64.deb
│   ├── libopencv-python_3.3.1-2-g31ccdfe11_arm64.deb
│   ├── libopencv-samples_3.3.1-2-g31ccdfe11_arm64.deb
│   ├── libopencv_3.3.1-2-g31ccdfe11_arm64.deb
│   ├── libvisionworks-repo_1.6.0.500n_arm64.deb
│   ├── libvisionworks-sfm-repo_0.90.4_arm64.deb
│   ├── libvisionworks-tracking-repo_0.88.2_arm64.deb
│   ├── python3-libnvinfer-dev_5.0.6-1+cuda10.0_arm64.deb
│   ├── python3-libnvinfer_5.0.6-1+cuda10.0_arm64.deb
│   ├── tensorrt_5.0.6.3-1+cuda10.0_arm64.deb
│   └── uff-converter-tf_5.0.6-1+cuda10.0_arm64.deb
└── nvidia_drivers.tbz2

1 directory, 21 files
```

* Build via `balena push $APPNAME`
* Copy wheels from the `/usr/src/app/$PACKAGE/dist/*.whl` (`main` service)
