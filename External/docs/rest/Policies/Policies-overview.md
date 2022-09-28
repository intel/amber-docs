# Placeholder - Policy Management Service (PS) Overview

Reference

Service:
API Version:


The Policy Management Service (PS) is a component responsible for managing policies containing SGX/TDX quote values
from platforms. The PS provides an interface for defining acceptable passlisted policies for data center servers.
These policies incorporate server firmware measurements, hardware capabilities, security technology information
and additional configuration. The measured data and configuration injected into the PS policies incorporate chain
of trust technology requirements for platform attestation.

Operation:

| Syntax       | Description                                                                                                       |
| :----------- | :-----------                                                                                                      |
| Get          | Searches for relevant policies and returns the signed policy collection consisting of all the associated policies.|
| Post         | Creates new policy in database.                                                                                   |
| Delete       | Deletes a policy by service offer type per tenant.                                                                |

Copyright (C) 2022 Intel Corporation. SPDX-License-Identifier: BSD-3-Clause

