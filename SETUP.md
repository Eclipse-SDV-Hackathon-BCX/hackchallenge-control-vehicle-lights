## Running Kuksa databroker

If Kuksa databroker is already a part of your challenge, you don't have to do anything.
Otherwise, download, build and run the databroker:

```
cd ..
git clone git@github.com:boschglobal/kuksa.val.git -b feature/subscribe_actuator_target
cd kuksa.val
cargo run --bin databroker -- --metadata data/vss-core/vss_release_3.0.json
```

Default address is `127.0.0.1` and port is `55555`

## Running SOME/IP - Kuksa bridge

To sync data betwwen KUKSA and SOME/IP we have an application which has to be running alongside KUKSA databroker.

Download the app and start it:

```
java -jar someip-kotlin-kuksa-taillight-all.jar --daemon-address=::1 --daemon-port=5555 --kuksa-address=127.0.0.1 --kuksa-port=55555
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
