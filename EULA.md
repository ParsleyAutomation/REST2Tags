# End User License Agreement

**REST to Tags** — a software module for Inductive Automation's Ignition platform
Parsley Automation ("PA")

Version 1.0. Effective on installation.

---

**Read this before installing.** By installing, copying, or using REST to Tags (the "Software"),
you agree to this Agreement. If you do not agree, do not install or use the Software.

## 1. Definitions

**Gateway** means a single installation of the Ignition platform, identified by the Gateway ID the
Software displays on its configuration page.

**Free Tier** means use of the Software without a valid License Key, which polls one distinct API
URL.

**License Key** means a key issued by PA that unlocks the Software beyond the Free Tier.

**You** means the individual or entity installing or using the Software.

## 2. License grant

Subject to this Agreement, PA grants You a non-exclusive, non-transferable, perpetual license to
install and use the Software.

**Free Tier.** You may install and use the Software on any number of Gateways without a License
Key, subject to the Free Tier limit and to every other term of this Agreement.

**Licensed use.** A License Key is issued for one Gateway, identified by its Gateway ID, unless the
key is expressly issued for multiple Gateways. A key marked with an expiry date grants use only
until that date.

**Backup and non-production.** You may install the Software on non-production Gateways used solely
for development, testing, staging, or disaster recovery of a licensed Gateway, at no additional
charge.

## 3. Restrictions

You may not:

a. Distribute, sublicense, rent, lease, or sell the Software to a third party, except that an
   integrator may install it on a Gateway owned by their client, provided that Gateway is licensed.
b. Reverse engineer, decompile, or disassemble the Software, except to the extent that applicable
   law expressly permits it despite this limitation.
c. Circumvent, disable, or interfere with the Free Tier limit, the License Key check, or any other
   licensing mechanism, or use a License Key on a Gateway it was not issued for.
d. Share, publish, or resell a License Key.
e. Remove or alter any copyright, trademark, or other proprietary notice.

## 4. Ownership

The Software is licensed, not sold. PA retains all right, title, and interest in the Software,
including all intellectual property rights. This Agreement grants You no rights other than the
license expressly stated in Section 2.

## 5. Your data and third-party services

The Software connects to HTTP endpoints You configure and reads data from them. PA does not
operate those endpoints, does not receive Your data, and does not transmit Your configuration,
credentials, or data to PA or any third party. The Software performs no license activation call
and requires no internet access to PA.

You are responsible for: the endpoints You configure, Your right to access them, compliance with
their terms of service, and the security of any credentials You enter. Credentials You enter are
stored on Your Gateway.

## 6. No warranty

THE SOFTWARE IS PROVIDED "AS IS" AND "AS AVAILABLE", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED. PA DISCLAIMS ALL WARRANTIES INCLUDING, WITHOUT LIMITATION, THE IMPLIED WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, TITLE, AND NON-INFRINGEMENT.

PA DOES NOT WARRANT THAT THE SOFTWARE WILL BE UNINTERRUPTED OR ERROR-FREE, THAT IT WILL OPERATE
WITH ANY PARTICULAR ENDPOINT OR VERSION OF IGNITION, OR THAT DATA IT RETRIEVES WILL BE ACCURATE,
CURRENT, OR AVAILABLE.

## 7. Not for safety-critical use

**The Software must not be used as the sole basis for any safety instrumented function, emergency
shutdown, alarm of last resort, protective interlock, or any other function where failure could
result in death, personal injury, environmental harm, or significant property damage.**

The Software retrieves data over networks You do not control, from services PA does not operate.
Network failures, endpoint outages, rate limiting, and incorrect or delayed third-party data are
foreseeable and normal. The Software reports data quality to the Ignition platform on a best-effort
basis; You are responsible for designing Your system so that a failure of the Software, or of any
endpoint it reads, results in a safe state.

## 8. Limitation of liability

TO THE MAXIMUM EXTENT PERMITTED BY LAW, PA SHALL NOT BE LIABLE FOR ANY INDIRECT, INCIDENTAL,
SPECIAL, CONSEQUENTIAL, OR EXEMPLARY DAMAGES, OR FOR ANY LOSS OF PROFITS, REVENUE, DATA, PRODUCTION,
OR BUSINESS INTERRUPTION, ARISING OUT OF OR RELATING TO THE SOFTWARE, HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGES.

PA'S TOTAL CUMULATIVE LIABILITY ARISING OUT OF OR RELATING TO THIS AGREEMENT SHALL NOT EXCEED THE
AMOUNT YOU ACTUALLY PAID PA FOR THE SOFTWARE IN THE TWELVE MONTHS PRECEDING THE EVENT GIVING RISE
TO THE CLAIM. WHERE THE SOFTWARE WAS OBTAINED AT NO CHARGE, PA'S TOTAL LIABILITY SHALL BE ZERO.

These limitations apply notwithstanding the failure of the essential purpose of any limited remedy.
Some jurisdictions do not allow certain exclusions or limitations, so parts of this Section may not
apply to You.

## 9. Support and updates

PA may, but is not obliged to, provide support or updates. Any support or update provided is
governed by this Agreement. PA may discontinue the Software at any time; a perpetual license
already granted survives discontinuation.

## 10. Term and termination

This Agreement is effective until terminated. It terminates automatically if You breach any of its
terms. On termination You must stop using the Software and remove it from all Gateways. Sections 3,
4, 6, 7, 8, and 11 survive termination.

An expired License Key does not terminate this Agreement; the Software reverts to the Free Tier.

## 11. General

**Governing law.** This Agreement is governed by the laws of the State of California, without
regard to its conflict of law rules. The exclusive venue for any dispute is the state and federal
courts located in California.

**Entire agreement.** This Agreement is the entire agreement between You and PA regarding the
Software and supersedes any prior understanding. It may be amended only in a writing signed by PA.

**Severability.** If any provision is held unenforceable, it shall be modified to the minimum extent
necessary to make it enforceable, and the remaining provisions remain in full force.

**No waiver.** A failure to enforce any provision is not a waiver of it.

**Assignment.** You may not assign this Agreement without PA's prior written consent, except to a
successor of Your entire business, provided the successor agrees to these terms.

**Third-party components.** The Software is built on the Ignition Module SDK and is subject to
Inductive Automation's own terms for the Ignition platform. The Software bundles no third-party
libraries.

---

Parsley Automation · parsleyautomation.com
