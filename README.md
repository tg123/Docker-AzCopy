# AzCopy Docker Image
Docker image for AzCopy v10, Windows and Linux

# Usage
<https://learn.microsoft.com/en-us/azure/storage/common/storage-use-azcopy-v10>

```
docker run farmer1992/azcopy
```

e.g. Upload `C:\test\123.txt` file to blob container

```
docker run --rm -v C:\test:C:\test farmer1992/azcopy copy C:\test\123.txt "https://account.blob.core.windows.net/mycontainer1/?sv=2018-03-28&ss=bjqt&srt=sco&sp=rwddgcup&se=2019-05-01T05:01:17Z&st=2019-04-30T21:01:17Z&spr=https&sig=MGCXiyEzbtttkr3ewJIh2AR8KrghSy1DGM9ovN734bQF4%3D" --recursive=true
```