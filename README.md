# cidr-plan

> An address plan you regenerate, instead of a spreadsheet you hope is current.

**Status:** 🚧 In development

## Overview

Allocate non-overlapping subnets from a supernet by requested size, emitting the plan as HCL, YAML or a table so an address plan stops living in a spreadsheet.

## Features

- Allocates by prefix length or by required host count, largest first, with no overlaps
- Declarative spec file: named subnets, grouped per tier or per availability zone
- Stable allocation, so appending a new subnet does not renumber the existing ones
- Emits Terraform `locals` HCL, YAML, JSON or a table; IPv4 and IPv6
- Reports free space and fragmentation left in the supernet after allocation
- Validates a plan against CIDRs already in use, to catch a collision before apply

## Stack

Go + net/netip, apparentlymart/go-cidr, hashicorp/hcl/v2 for HCL output, cobra.

## Usage

```bash
cidr-plan --supernet 10.42.0.0/16 --spec network.yaml --format hcl --out cidrs.tf
```

## License

MIT

---

Archived on 2026-11-05. The idea moved to [subnetcalc](https://github.com/moveeeax/subnetcalc/issues/3).
