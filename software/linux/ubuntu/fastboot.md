


# Fastboot

"Fastboot is a protocol and a tool of the same name. It is included with the Android SDK package used primarily to modify the flash filesystem via a USB connection from a host computer. It requires that the device be started in Fastboot mode." - [Fastboot Wikipedia Article](https://en.wikipedia.org/wiki/Fastboot)

## Installation

1. Install prerequisites

```
sudo apt install libarchive-tools
```

2. Download

```
curl -O https://dl.google.com/android/repository/platform-tools_r33.0.1-linux.zip
```

3. Check download

```
echo 'a339548918c3ab31c4d88416c21cee753bd942040540216c06e640f4b6db3ae2  platform-tools_r33.0.1-linux.zip' | sha256sum -c
```

4. Extract

```
bsdtar xvf platform-tools_r33.0.1-linux.zip
```

5. Set PATH

```
export PATH="$PWD/platform-tools:$PATH"
```

6. Check version

```
fastboot --version
```


