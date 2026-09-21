# ust-axiom

## Overview

`ust-axiom` is the primary production server. It hosts containerized applications, ZFS storage, media services, and local AI workloads.

| Property | Value |
| --- | --- |
| Role | Production / Storage |
| Network | VLAN 20 |
| Address | `192.168.20.108` |
| CPU | Intel Core i5-9400F |
| Memory | 16 GB DDR4 |
| GPU | NVIDIA Tesla P40 24GB VRAM|
| Storage | 8 × 512 GB SSD RAIDZ2 |
| Operating System | Ubuntu Linux |

## Services

| Service | Purpose |
| --- | --- |
| Jellyfin | Media streaming |
| Immich | Personal Photos |
| Open WebUI | Local AI interface |
| Ollama | Local model inference |
| Home Assistant | Home automation |
| node_exporter | Prometheus host metrics |

## Storage Layout

TBA (Needs Organization)

## Management

Applications are accessed through Nginx on `ust-overseer`. Backend ports are limited to the reverse proxy and required management systems.

