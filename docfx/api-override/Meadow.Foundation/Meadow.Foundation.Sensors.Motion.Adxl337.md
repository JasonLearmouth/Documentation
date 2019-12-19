---
uid: Meadow.Foundation.Sensors.Motion.Adx337
remarks: *content
---

| ADXL337       |             |
|---------------|-------------|
| Status        | Working     |
| Source code   | [GitHub](https://github.com/WildernessLabs/Meadow.Foundation/tree/master/Source/Meadow.Foundation.Peripherals/Sensors.Motion.Adxl337) |
| NuGet package | ![NuGet](https://img.shields.io/nuget/v/Meadow.Foundation.Sensors.Motion.Adxl337.svg?label=NuGet) |
| | |

The **ADXL337** is a low power accelerometer capable of measuring +/- 3g of acceleration along three axes. The ADXL337 is controlled via I2C.

### Code Example

```csharp
public class MeadowApp : App<F7Micro, MeadowApp>
{
    Adxl337 sensor;

    public MeadowApp()
    {
        sensor = new Adxl337(Device, Device.Pins.A01, Device.Pins.A02, Device.Pins.A03, 500);

        sensor.AccelerationChanged += Sensor_AccelerationChanged;
    }

    private void Sensor_AccelerationChanged(object sender, Meadow.Foundation.Sensors.SensorVectorEventArgs e)
    {
        Console.WriteLine($"X: {e.CurrentValue.X}, Y: {e.CurrentValue.Y}, Z: {e.CurrentValue.Z}");
    }
}
```

### Wiring Example

![](../../API_Assets/Meadow.Foundation.Sensors.Motion.Adx337/Adx337_Fritzing.svg)