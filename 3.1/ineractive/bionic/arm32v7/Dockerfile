ARG REPO=mcr.microsoft.com/dotnet/core/sdk
FROM $REPO:3.1-bionic-arm32v7

# Opt out of telemetry until after we install jupyter when building the image, this prevents caching of machine id
ENV DOTNET_TRY_CLI_TELEMETRY_OPTOUT=true

# Install lastest build from master branch of Microsoft.DotNet.Interactive from myget
RUN dotnet tool install --tool-path /usr/share/dotnet-interactive Microsoft.dotnet-interactive --add-source "https://dotnet.myget.org/F/dotnet-try/api/v3/index.json"
RUN ln -s /usr/share/dotnet-interactive/dotnet-interactive /usr/bin/dotnet-interactive

# Enable telemetry once we install jupyter for the image
ENV DOTNET_TRY_CLI_TELEMETRY_OPTOUT=false