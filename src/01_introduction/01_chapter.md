# Introduction

Hyperbase is an open source Backend-as-a-Service (BaaS) that strives to be performant and reliable. It provides a way for developers to handle common backend functionalities without having to build and maintain them from scratch. This can save time and resources, allowing developers to focus on the core features of their application.

## Key features

- Fast and reliable backend to serve hundreds of thousands requests per second.

- Secure data management with strict access control using auth token.

- Implementing schema-based database, always check the data type before inserting it into the database to prevent unexpected bugs.

- Realtime subscriptions through WebSocket to notify any eligible connected devices for each data changes.

- Simple but expressive querying using REST API.

- Supports data insertion over an MQTT connection, allowing microcontrollers to integrate easily.

- Supports file storage in any format.

- Delete data or files after specified time-to-live (TTL), if set.

- Works with various SQL database backends, you can choose between PostgreSQL, MySQL, SQLite, or any other database compatible with any of the three.

- Synchronize data to other Hyperbase instances using the <a href="https://en.wikipedia.org/wiki/Gossip_protocol" target="_blank">gossip protocol</a> (currently only available if using PostgreSQL, MySQL, or SQLite)
