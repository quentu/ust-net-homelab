# Naming Standard

## Hostnames

All infrastructure hosts use the prefix:

```text
ust-
```

Format:

```text
ust-<identity>
```

Cluster members use:

```text
ust-<cluster-name>-##
```

Examples:

```text
ust-overseer
ust-axiom
ust-vault
ust-sentinel-01
ust-sentinel-02
```

## Naming Philosophy

Physical hosts receive durable identity-based names.

Examples:

- `overseer` — management/control
- `axiom` — production/critical
- `vault` — backup
- `sentinel` — compute nodes

Services use descriptive DNS names instead of inheriting hostnames.

Examples:

```text
jellyfin.intra.quentu.dev
photos.intra.quentu.dev
```

This allows services to move between hosts without changing their user-facing address.

## Containers

Docker Compose project directories are formatted to explicitly match the service:

```text
compose-files/
├── jellyfin/
│   └── compose.yml
├── immich/
│   └── compose.yml
└── open-webui/
    └── compose.yml
```

Preferred Compose filename:

```text
compose.yml
```

## Virtual Machines

Default format:

```text
<role>-##
```

or, when identity matters:

```text
<service>-##
```
If intended to be disposable / a testing enviorment:

```test
lab-<xyz>-##
````

Examples:

```text
lab-pentest-01
lab-arch-01
win11-01
```
