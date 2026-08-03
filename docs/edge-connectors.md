# Supported edge connectors

Asset Insights Portal connects to the sources your sites already run, over the protocols they already speak.

## What you can connect today

There are two routes onto the platform and both are open now.

The first is a field gateway. Every gateway is built on a shared software development kit that already handles the demanding parts: signing each package, buffering to disk when a site loses connectivity, retrying with backoff until delivery is confirmed, and opening outbound connections only so your plant network stays closed. Bringing a source online means writing the part that reads your protocol, because everything between that read and the harmonized model is already built and running. The Bluetooth gateway for corrosion and condition sensors is in production today, and the same machinery drives both streaming sources that push as readings arrive and polled sources on a set cadence.

The second route is your own systems. The ingest API is documented and open, so a historian, a middleware layer, or an edge application you already run can authenticate with its own credentials and post signed data straight into the platform. You do not have to wait for a native connector before you start moving data.

The canonical model runs ahead of the connector list as well. It already covers environmental readings such as ambient temperature, humidity, and wind speed, mechanical signals including pitch angle, yaw angle, gearbox oil temperature, and rotational speeds, and a standard set of turbine and sensor alarm classes. By the time a connector for your equipment arrives, the model it harmonizes into is defined, versioned, and in use.

Tell us what your sites run and we will map it to the fastest way in, whether that is a gateway that exists, a push from a system you own, or a connector we build with you.

## Native connectors available now

- Bluetooth, for corrosion and condition sensors

## Native connectors coming

- OPC UA, for wind SCADA including Vestas, Nordex, Gamesa, and Senvion
- MQTT, for streaming telemetry
- File-based sources, including FTP
- Modbus TCP, for solar PV inverters, meters, and balance-of-plant devices
- Vestas Fast Log
- Vestas 10 min data
- SGRE LAC
- SGRE 10 min data
- Siemens XML RPC
- IEC 104
- Zabbix
- ADA
- HPPP

## Need a specific protocol?

Tell us what your sites run. We are ready to extend the list with new protocols, so [get in touch](get-in-touch.md) and we will look at adding it.

That covers what the platform connects to. Next, what runs underneath it: [architecture](architecture.md).
