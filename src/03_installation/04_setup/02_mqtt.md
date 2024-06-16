# MQTT

The first step is to setup MQTT broker. Hyperbase uses MQTT to allow any microcontrollers or other devices to insert data through message publishing via a specific MQTT topic defined in [Hyperbase config file](04_hyperbase.md). We recommend [EMQX](https://www.emqx.io/) as the MQTT broker. The easiest way is to install it from [the Docker Hub](https://hub.docker.com/_/emqx).

You need to configure MQTT authentication and authorization once Hyperbase is running to prevent security issues. You can follow [the Post-installation section](../05_post_installation.md).
