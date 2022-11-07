## Running Kuksa databroker

To use the lights you need a *modified* version of the KUKSA databroker.

Download, build and run the databroker:

```
cd ..
git clone git@github.com:boschglobal/kuksa.val.git -b feature/subscribe_actuator_target
cd kuksa.val
cargo run --bin databroker -- --metadata data/vss-core/vss_release_3.0.json
```

Default address for Kuksa is `127.0.0.1` and port is `55555`

## Running SOME/IP - Kuksa bridge

To sync data betwwen KUKSA and SOME/IP we have a JVM application which has to be running alongside KUKSA databroker.

Download the [release](https://github.com/Eclipse-SDV-Hackathon-BCX/hackchallenge-control-vehicle-lights/releases/tag/hackaton) and start it:

```
java -jar someip-kotlin-kuksa-taillight-all.jar --daemon-address=10.52.250.33 --daemon-port=5555 --kuksa-address=127.0.0.1 --kuksa-port=55555
```

You should see output like this:
```
2022-11-07 17:03:34.893 INFO  KuksaSomeIpBridge Welcome to SommR-Kuksa bridge!
2022-11-07 17:03:34.912 INFO  KuksaSomeIpBridge Kuksa databroker topics:
2022-11-07 17:03:34.912 INFO  KuksaSomeIpBridge > Vehicle.Body.Lights.IsBackupOn
2022-11-07 17:03:34.912 INFO  KuksaSomeIpBridge > Vehicle.Body.Lights.IsBrakeOn
2022-11-07 17:03:34.912 INFO  KuksaSomeIpBridge > Vehicle.Body.Lights.IsLeftIndicatorOn
2022-11-07 17:03:34.912 INFO  KuksaSomeIpBridge > Vehicle.Body.Lights.IsRunningOn
2022-11-07 17:03:34.912 INFO  KuksaSomeIpBridge 
2022-11-07 17:03:34.912 INFO  KuksaSomeIpBridge More info: https://github.com/Eclipse-SDV-Hackathon-BCX/hackchallenge-control-vehicle-lights#readme
2022-11-07 17:03:34.912 INFO  KuksaSomeIpBridge 
2022-11-07 17:03:34.913 INFO  KuksaSomeIpBridge Connecting to SommR 10.52.250.33:5555
2022-11-07 17:03:34.933 INFO  KuksaSomeIpBridge Connecting to Kuksa 127.0.0.1:55555
2022-11-07 17:03:35.213 INFO  KuksaSomeIpBridge Connected to Kuksa 127.0.0.1:55555
2022-11-07 17:03:35.249 INFO  KuksaSomeIpBridge Connected to SommR 10.52.250.33:5555
2022-11-07 17:03:35.276 INFO  KuksaSomeIpBridge Found TailLight service
```

## Running Kuksa CLI

Test it with CLI:

```
cargo run --bin databroker-cli
client> set Vehicle.Body.Lights.IsBrakeOn true
-> Ok
client> set Vehicle.Body.Lights.IsBrakeOn false
-> Ok

```

## Kuksa Topics

* Vehicle.Body.Lights.IsLeftIndicatorOn
* Vehicle.Body.Lights.IsRunningOn
* Vehicle.Body.Lights.IsBrakeOn
* Vehicle.Body.Lights.IsBackupOn
