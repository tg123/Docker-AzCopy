# AzCopy Docker Image
Docker image for AzCopy <https://docs.microsoft.com/en-us/azure/storage/storage-use-azcopy>

# Usage 

```
docker run farmer1992/docker-azcopy
```

e.g. Upload `C:\test\123.txt` file to blob container

```
docker run --rm -v C:\test:C:\copy  farmer1992/docker-azcopy AzCopy /Source:"C:\copy\" /Pattern:123.txt /Dest:"https://test.blob.core.windows.net/test" /DestKey:....KEY.....
```
