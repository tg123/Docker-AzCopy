# AzCopy Docker Image
Docker image for AzCopy

# Usage [Windows]
<https://docs.microsoft.com/en-us/azure/storage/storage-use-azcopy>

![Docker Build](https://farmer1992.visualstudio.com/_apis/public/build/definitions/3686302e-40e0-495b-a6f8-f2926767661b/8/badge)

```
docker run farmer1992/azcopy
```

e.g. Upload `C:\test\123.txt` file to blob container

```
docker run --rm -v C:\test:C:\copy  farmer1992/azcopy AzCopy /Source:"C:\copy\" /Pattern:123.txt /Dest:"https://test.blob.core.windows.net/test" /DestKey:....KEY.....
```

# Usage [linux]
<https://docs.microsoft.com/en-us/azure/storage/storage-use-azcopy-linux>

```
docker run farmer1992/azcopy:linux-latest
```
