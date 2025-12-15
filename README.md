# Cellular Intelligence

Plug-and-play RF fingerprinting and cellular geolocation with ML.

## Quick Start

```bash
dotnet restore
dotnet build
```

```csharp
using CellularIntelligence;

var cell = new CellularIntelligence(modemPort: "COM3");
await cell.StartAsync();
var status = cell.GetStatusSummary();
var location = await cell.EstimateLocationAsync();
```

## Components

| File | Purpose |
|------|---------|
| CellularIntelligence.cs | Main orchestrator |
| ATCommandParser.cs | AT command response parsing |
| ModemController.cs | Serial modem communication |
| RFLocatorModel.cs | ML.NET RF fingerprinting |
| HandoverPredictor.cs | LSTM handover prediction |
| CellularModels.cs | Data models |
| OpenCellIDImporter.cs | Cell tower database import |
| CellularAccessPoint.cs | Cellular AP capabilities |
| CellTrainingTool.cs | Training data collection |

## Features

- Real-time cellular signal polling
- RF fingerprinting for GPS-free geolocation
- Predictive handover recommendations
- Drive-test data collection mode
- OpenCellID integration

## Requirements

- .NET 8.0+
- Microsoft.ML (auto-restored)
- USB cellular modem (for real data)
- Serial port access
