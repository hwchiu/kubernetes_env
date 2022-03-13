FROM ubuntu:18.04

RUN apt-get update
RUN apt-get install -y wget 

RUN wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb 
RUN dpkg -i packages-microsoft-prod.deb

RUN apt-get update
RUN apt-get install -y dotnet-runtime-3.1 apt-transport-https dotnet-sdk-3.1

COPY copy_example /tmp/copy_example


ENTRYPOINT ["dotnet", "run", "--project=/tmp/copy_example/"]
