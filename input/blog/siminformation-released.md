---
Title: SimInformation released
Published: 2016/02/02
Tags:
  - xamarin
  - uwp
  - mobile sim
  - ICCID
  - MCC
  - IMSI
  - MSID
  - MNC
  - MSISDN
---

[SimInformation](https://github.com/ghuntley/siminformation) is a cross-platform library that provides a way to access the following information from your SIM card:

* Integrated Circuit Card ID. (ICCID)
* Mobile Country Code. (MCC)
* International Mobile Subscriber Identity. (IMSI)
* Mobile Station ID. (MSID)
* Mobile Network Code. (MNC)
* Mobile Subscriber International ISDN Number. (MSISDN)

## Usage

The API is rather straight forward

```csharp
var simInformation = new SimInformation();
IReadOnlyList<SimCard> simCards = simInformation.GetAllCards();

simCards[x].ICCID
simCards[x].MCC
simCards[x].IMSI
simCards[x].MSID
simCards[x].MNC
simCards[x].MSIDN
```

Instead of newing up the implementation each time you need it, register it into your IoC/DI container:

```csharp
// example registration using splat
Locator.CurrentMutable.RegisterConstant(() => new SimInformation(), typeof(ISimInformation));
```

Then use it in your viewmodel or services as needed:

```csharp
// example integration with reactiveui
public class MyCoolViewModel : ReactiveObject
{
    private readonly ISimInformation _simInformation;

    public MyCoolViewModel(ISimInformation simInformation = null)
    {
        _simInformation = simInformation ?? Locator.Current.GetService<ISimInformation>();
    }
}
```
