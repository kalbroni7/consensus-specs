# EIP4844 Light Client -- Networking

**Notice**: This document is a work-in-progress for researchers and implementers.

## Table of contents

<!-- TOC -->
<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Networking](#networking)
  - [The gossip domain: gossipsub](#the-gossip-domain-gossipsub)
    - [Topics and messages](#topics-and-messages)
      - [Global topics](#global-topics)
        - [`light_client_finality_update`](#light_client_finality_update)
        - [`light_client_optimistic_update`](#light_client_optimistic_update)
  - [The Req/Resp domain](#the-reqresp-domain)
    - [Messages](#messages)
      - [GetLightClientBootstrap](#getlightclientbootstrap)
      - [LightClientUpdatesByRange](#lightclientupdatesbyrange)
      - [GetLightClientFinalityUpdate](#getlightclientfinalityupdate)
      - [GetLightClientOptimisticUpdate](#getlightclientoptimisticupdate)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->
<!-- /TOC -->

## Networking

The [Capella light client networking specification](../../capella/light-client/p2p-interface.md) is extended to exchange [EIP4844 light client data](./sync-protocol.md).

### The gossip domain: gossipsub

#### Topics and messages

##### Global topics

###### `light_client_finality_update`

[0]: # (eth2spec: skip)

| `fork_version`                                         | Message SSZ type                      |
| ------------------------------------------------------ | ------------------------------------- |
| `GENESIS_FORK_VERSION`                                 | n/a                                   |
| `ALTAIR_FORK_VERSION` through `BELLATRIX_FORK_VERSION` | `altair.LightClientFinalityUpdate`    |
| `CAPELLA_FORK_VERSION`                                 | `capella.LightClientFinalityUpdate`   |
| `EIP4844_FORK_VERSION` and later                       | `eip4844.LightClientFinalityUpdate`   |

###### `light_client_optimistic_update`

[0]: # (eth2spec: skip)

| `fork_version`                                         | Message SSZ type                      |
| ------------------------------------------------------ | ------------------------------------- |
| `GENESIS_FORK_VERSION`                                 | n/a                                   |
| `ALTAIR_FORK_VERSION` through `BELLATRIX_FORK_VERSION` | `altair.LightClientOptimisticUpdate`  |
| `CAPELLA_FORK_VERSION`                                 | `capella.LightClientOptimisticUpdate` |
| `EIP4844_FORK_VERSION` and later                       | `eip4844.LightClientOptimisticUpdate` |

### The Req/Resp domain

#### Messages

##### GetLightClientBootstrap

[0]: # (eth2spec: skip)

| `fork_version`                                         | Response SSZ type                     |
| ------------------------------------------------------ | ------------------------------------- |
| `GENESIS_FORK_VERSION`                                 | n/a                                   |
| `ALTAIR_FORK_VERSION` through `BELLATRIX_FORK_VERSION` | `altair.LightClientBootstrap`         |
| `CAPELLA_FORK_VERSION`                                 | `capella.LightClientBootstrap`        |
| `EIP4844_FORK_VERSION` and later                       | `eip4844.LightClientBootstrap`        |

##### LightClientUpdatesByRange

[0]: # (eth2spec: skip)

| `fork_version`                                         | Response chunk SSZ type               |
| ------------------------------------------------------ | ------------------------------------- |
| `GENESIS_FORK_VERSION`                                 | n/a                                   |
| `ALTAIR_FORK_VERSION` through `BELLATRIX_FORK_VERSION` | `altair.LightClientUpdate`            |
| `CAPELLA_FORK_VERSION`                                 | `capella.LightClientUpdate`           |
| `EIP4844_FORK_VERSION` and later                       | `eip4844.LightClientUpdate`           |

##### GetLightClientFinalityUpdate

[0]: # (eth2spec: skip)

| `fork_version`                                         | Response SSZ type                     |
| ------------------------------------------------------ | ------------------------------------- |
| `GENESIS_FORK_VERSION`                                 | n/a                                   |
| `ALTAIR_FORK_VERSION` through `BELLATRIX_FORK_VERSION` | `altair.LightClientFinalityUpdate`    |
| `CAPELLA_FORK_VERSION`                                 | `capella.LightClientFinalityUpdate`   |
| `EIP4844_FORK_VERSION` and later                       | `eip4844.LightClientFinalityUpdate`   |

##### GetLightClientOptimisticUpdate

[0]: # (eth2spec: skip)

| `fork_version`                                         | Response SSZ type                     |
| ------------------------------------------------------ | ------------------------------------- |
| `GENESIS_FORK_VERSION`                                 | n/a                                   |
| `ALTAIR_FORK_VERSION` through `BELLATRIX_FORK_VERSION` | `altair.LightClientOptimisticUpdate`  |
| `CAPELLA_FORK_VERSION`                                 | `capella.LightClientOptimisticUpdate` |
| `EIP4844_FORK_VERSION` and later                       | `eip4844.LightClientOptimisticUpdate` |
