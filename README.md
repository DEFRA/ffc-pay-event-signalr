# FFC Pay Event SignalR

> An [Azure Function app](https://azure.microsoft.com/en-gb/services/functions/)
> for sending real-time events to
> [ffc-pay-event-monitor](https://github.com/DEFRA/ffc-pay-event-monitor)

## Prerequisites

- [SignalR Service Instance](https://docs.microsoft.com/en-us/azure/azure-signalr/signalr-quickstart-azure-functions-javascript#create-an-azure-signalr-service-instance)

## Signal R

Azure SignalR Service simplifies the process of adding real-time web functionality to applications over HTTP. This real-time functionality allows the service to push content updates to connected clients, such as a single page web or mobile application. As a result, clients are updated without the need to poll the server, or submit new HTTP requests for updates.

[SignalR overview](https://docs.microsoft.com/en-us/azure/azure-signalr/signalr-overview)

## SignalR Negotiate
 - A negotiate endpoint is exposed by Azure SignalR Service SDK for each hub.
 - This endpoint will respond to client's negotiation requests and redirect clients to SignalR Service.
 - Eventually, clients will be connected to SignalR Service.

[SignalR concept internals](https://docs.microsoft.com/en-us/azure/azure-signalr/signalr-concept-internals#server-connections)

## Function Development

The best place to start for an overall view of how JavaScript Functions work in
Azure is the
[Azure Functions JavaScript developer guide](https://docs.microsoft.com/en-us/azure/azure-functions/functions-reference-node?tabs=v2).
From there follow the appropriate link to the documentation specific to
your preferred development environment i.e.
[Visual Studio Code](https://docs.microsoft.com/en-us/azure/azure-functions/create-first-function-vs-code-node)
or
[command line](https://docs.microsoft.com/en-us/azure/azure-functions/create-first-function-cli-node?tabs=azure-cli%2Cbrowser).

The documentation within this repo assumes the `command line` setup has been
completed, specifically for
[Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli).

## Running Locally

`npm start`

## Configuration - Application Settings

Currently the deployment of application settings is manual and can be edited in either the Azure portal or via the Azure CLI

### Example

Through the Azure CLI app settings can be set via the use of a json file

settings.json

```
[
  {
    "name": "AZURE_STORAGE_USE_CONNECTION_STRING",
    "value": ""
  }
]
```

azure CLI command

```
az login

az functionapp config appsettings set --name "$FUNCTION_APP_NAME" --resource-group "$RESOURCE_GROUP" --settings @settings.json
```

## License

THIS INFORMATION IS LICENSED UNDER THE CONDITIONS OF THE OPEN GOVERNMENT
LICENCE found at:

<http://www.nationalarchives.gov.uk/doc/open-government-licence/version/3>

The following attribution statement MUST be cited in your products and
applications when using this information.

> Contains public sector information licensed under the Open Government license
> v3

### About the license

The Open Government Licence (OGL) was developed by the Controller of Her
Majesty's Stationery Office (HMSO) to enable information providers in the
public sector to license the use and re-use of their information under a common
open licence.

It is designed to encourage use and re-use of information freely and flexibly,
with only a few conditions.

