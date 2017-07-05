FROM microsoft/windowsservercore:latest
MAINTAINER Boshi Lian <farmer1992@gmail.com>

ENV AZ_COPY_URL http://az837173.vo.msecnd.net/azcopy-6-1-0/MicrosoftAzureStorageTools.msi
ENV AZ_COPY_VERSION 6.1.0

RUN powershell -NoProfile -Command \
        Invoke-WebRequest %AZ_COPY_URL% -OutFile MicrosoftAzureStorageTools.msi;

RUN msiexec /i MicrosoftAzureStorageTools.msi /qn

RUN powershell -NoProfile -Command \
        Remove-Item -Force MicrosoftAzureStorageTools.msi;

RUN setx /M AZ_COPY_HOME "%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy"

RUN setx /M PATH "%PATH%;%AZ_COPY_HOME%"

CMD ["AzCopy.exe"]
