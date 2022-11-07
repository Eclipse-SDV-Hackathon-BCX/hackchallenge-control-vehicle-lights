# Eclipse SDV Hackathon on BCX2022

# Welcome to the "Control vehicle lights" hack challenge!

* Control vehicle lights using Eclipse [SommR](https://projects.eclipse.org/projects/automotive.sommr) and [KUKSA.val databroker](https://github.com/eclipse/kuksa.val/tree/master/kuksa_databroker#readme)
* Integrate lights with other hack challenges

## Challenge details

Our Retro-suitcase houses a VW T2 light retrofitted with a SOME/IP ECU (Electronic Control Unit).
Another board runs Eclipse SommR daemon providing access to the service for hack participants.
Use Eclipse [KUKSA.val databroker](https://github.com/eclipse/kuksa.val/tree/master/kuksa_databroker#readme)
to control the lights or read their state.
Alternatively, the service can be accessed directly from Rust, Java or Kotlin applications.

[Challenge details](./SETUP.md)

## Integration with other challenges

Our hack challenge is intended to *complement* other hack challenges, for example [Passenger welcome](https://github.com/Eclipse-SDV-Hackathon-BCX/hackchallenge-passenger-welcome) or [Driving Score](https://github.com/Eclipse-SDV-Hackathon-BCX/hackchallenge-driving-score). For example, you can add blinking sequences to these challenges. Since we use [KUKSA.val databroker](https://github.com/eclipse/kuksa.val/tree/master/kuksa_databroker#readme) as a mediator,
additional effort to access the lights is minimal.

## Challenge setup

![image](https://user-images.githubusercontent.com/827794/199997772-ec990e1c-b623-4aef-a12b-b18e4964ad70.png)

## About Eclipse SommR project

![image](https://user-images.githubusercontent.com/827794/199989346-6766e11e-36ac-4318-b636-0fa5e9b303b6.png)

Eclipse SommR provides access to vehicle ECUs (Electronic Control Unit) for car applications written in Rust, C++, Java or Kotlin. 

Eclipse SommR daemon interacts with vehicle ECUs using SOME/IP protocol and hides the complexities related to it from client applications. Applications use SommR SDK to access SOME/IP services in a typesafe and convenient way. SDK will be available for Rust, C++, Java and Kotlin. The daemon is written in Rust.
