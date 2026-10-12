# Industrial Operations & Fiscal Platform

> Technical showcase of a proprietary B2B platform for industrial operations,
> shipping verification, pre-invoicing and governed Brazilian fiscal workflows.

[Leia em portugues](README.pt-BR.md) | [Architecture](ARCHITECTURE.md) |
[Technical evidence](EVIDENCE.md) | [Current status](STATUS.md) |
[Evaluation process](EVALUATION.md)

## Purpose of this repository

This public repository presents the problem addressed, the architecture, the
engineering evidence and the current maturity of a proprietary software asset.

It was created for qualified conversations with:

- potential acquirers of the source code and intellectual asset;
- strategic partners interested in validating and evolving the product;
- fiscal and technology specialists capable of supporting external validation;
- organizations evaluating a controlled pilot or technical due diligence.

This is not the source-code repository and it is not an open-source release.

## Product thesis

Industrial shipping and invoicing often depend on disconnected steps: printed
maps, manual verification, handwritten corrections, file exchanges and repeated
interpretation of the same information.

The platform was designed to create a traceable chain between physical
operations and fiscal preparation:

```mermaid
flowchart LR
    A[Order] --> B[Shipping Planning]
    B --> C[Packing and Identification]
    C --> D[Physical Verification]
    D --> E[Structured Operational Result]
    E --> F[Pre-Invoicing]
    F --> G[Fiscal Context]
    G --> H[Governed Fiscal Determination]
    H --> I[Immutable Snapshot]
    I --> J[Issuance Contract]
```

The central principle is simple: the fiscal layer must not silently invent a
tax decision when governed coverage is missing.

## Main capabilities

### Industrial operations

- map and order processing;
- packing and QR-code identification;
- digital and hybrid verification;
- quantities, components, sets, reservations and leftovers;
- movement traceability and operational history;
- structured handoff to invoicing.

### Fiscal preparation

- canonical fiscal context;
- governed coverage matrix;
- reusable federal and state treatments;
- review, approval, publication and revocation lifecycle;
- tax determination and materialization;
- immutable fiscal snapshot;
- issuance contract and provider-adapter boundary;
- explicit pending states when coverage is absent or incomplete.

### Product infrastructure

- versioned database migrations;
- fresh-install and upgrade paths;
- backup, restore and operational rollback strategy;
- internal issuance resilience and idempotency;
- document distribution outbox;
- receivables and collection architecture;
- role segregation for invoicing, fiscal approval and treasury;
- automated regression gates.

## Current maturity

| Area | Current evidence |
|---|---|
| Industrial operations | Used in a real industrial workflow |
| Fiscal architecture | Advanced implementation and internal validation |
| Headless fiscal path | Controlled proof completed |
| Installation and recovery | Internally tested |
| External NF-e homologation | Pending controlled pilot |
| Nationwide fiscal coverage | Requires client-specific governance and validation |

The project deliberately separates these states:

```text
implemented
tested internally
used operationally
proved in a controlled POC
externally homologated
```

They are not treated as equivalent.

## Architectural highlights

- modular monolith with explicit domain boundaries;
- fiscal core executable without the web interface in the proved scenario;
- canonical context with twelve causal dimensions;
- fiscal decisions separated from UI and provider adapters;
- transaction results frozen before issuance;
- historical snapshots protected from later configuration changes;
- explicit handling of missing coverage instead of silent fallback;
- provider integrations kept behind contracts and adapters.

See [ARCHITECTURE.md](ARCHITECTURE.md) for the architectural view.

## Technical evidence

The public evidence includes:

- incremental refactoring protected by dedicated tests;
- quick, integration and release regression gates;
- database integrity checks;
- a headless POC reaching the issuance-adapter boundary;
- snapshot immutability checks;
- internal NF-e lifecycle and recovery tests;
- documented limits of what has and has not been externally proved.

See [EVIDENCE.md](EVIDENCE.md) for scope and limitations.

## What remains before commercial operation

The principal remaining frontier is not presented as already complete:

1. define the first pilot's contracted scope;
2. configure the real company, issuer and governed fiscal coverage;
3. provide valid certificates and external credentials;
4. execute controlled provider and SEFAZ homologation;
5. validate the sold scenarios with the responsible fiscal authority;
6. approve operational go-live criteria.

Client-specific tax decisions, credentials and external homologation are not
replaced by synthetic data or internal mocks.

## Evaluation and acquisition

The intended transaction is the controlled evaluation and possible acquisition
of the proprietary source code and its technical assets, not public code
distribution.

A qualified due-diligence process may include, under an appropriate private
channel and confidentiality terms:

- supervised source-code review;
- architecture and data-model review;
- migration and regression evidence;
- controlled product demonstration;
- release-candidate inspection;
- roadmap, known limitations and external dependencies;
- transfer and continuation planning.

Initial contact should be made through the maintainer's GitHub profile. Do not
publish confidential, operational or security information in public issues.

## Confidentiality boundary

This showcase does not publish:

- proprietary source code;
- real company or client identities;
- operational documents or transaction-level data;
- credentials, tokens, certificates or environment references;
- production databases or backups;
- company-specific fiscal rules;
- internal product names or private repository paths.

See [CONFIDENTIALITY.md](CONFIDENTIALITY.md) for the publication boundary.

## Rights

Copyright 2026. All rights reserved.

No license to use, copy, modify, distribute or commercially exploit the
proprietary product is granted by this public technical showcase.
