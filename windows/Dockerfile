FROM mcr.microsoft.com/windows/nanoserver:ltsc2022
LABEL maintainer="Boshi Lian<farmer1992@gmail.com>"

ENV AZ_COPY_HOME "C:\azcopy"

RUN curl -L -o azcopy.zip https://aka.ms/downloadazcopy-v10-windows
RUN tar -xvf azcopy.zip
RUN del azcopy.zip
RUN for /d %i in ("azcopy_windows_*") do move %~nxi %AZ_COPY_HOME%

RUN setx PATH "%PATH%;%AZ_COPY_HOME%"

CMD ["azcopy.exe"]
