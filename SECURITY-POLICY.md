# Double Open Vulnerability Handling Policy

Version 1.0, 2026-09-10

## 1. Purpose and scope

This policy describes how Double Open Oy ("Double Open", "we") receives, handles, and discloses reports of security vulnerabilities.

It applies to:

* Software maintained by Double Open in the GitHub organization [doubleopen-io](https://github.com/doubleopen-io), including Double Open's modifications in forks of upstream projects until those modifications are merged upstream;
* Services operated by Double Open, including hosted ORT Server instances and the [doubleopen.io](https://doubleopen.io) website;
* Double Open's own IT infrastructure, to the extent a vulnerability there could affect customers or users.

It does not cover vulnerabilities in third-party software that Double Open merely uses or forks without modification.
We will try to help route such reports to the right upstream project.

## 2. Definitions

* **Vulnerability**: a weakness, susceptibility, or flaw in software or a service that can be exploited by a cyber threat.
  This follows the definition in Article 3(40) of Regulation (EU) 2024/2847 (Cyber Resilience Act).
  Whether a vulnerability is exploitable under practical operational conditions, in the sense of Article 3(41), affects how we resolve it, not whether we accept the report.
* **Security Team**: the Double Open staff members who receive emails sent to security@doubleopen.io and are responsible for triage and coordination.
* **Reporter**: any person or organization submitting a vulnerability report.

## 3. Security Team

The Security Team consists of three named Double Open staff members.
All three receive every report sent to security@doubleopen.io.
One of them acts as coordinator for each report.
Membership is recorded internally.
The team has authority to:

* create and edit private GitHub security advisories in all repositories,
* request an embargo on a fix until coordinated disclosure,
* request CVE identifiers,
* decide on public disclosure timing together with Double Open management.

The team does not itself fix every issue.
Maintainers of the affected repository or service are responsible for developing the fix; the Security Team coordinates.

## 4. How to report

Reports are accepted through:

1. Email to **security@doubleopen.io** (preferred).
2. GitHub private vulnerability reporting on the affected repository.

Reports must not be filed as public issues, discussions, or pull requests.
If a report is filed publicly by mistake, we will ask the reporter to delete it and will treat the issue as already disclosed when deciding on timing.

## 5. What reporters can expect

| Step | Target |
|------|--------|
| Acknowledgment of receipt | within 3 business days |
| Initial assessment (accepted / not a vulnerability / out of scope) | within 10 business days |
| Status updates | at least every 14 days while the issue is open |
| Fix and coordinated disclosure | target 90 days from acknowledgment; sooner for critical issues, later only by agreement with the reporter |

We will:

* handle the report confidentially and share it only with people who need to know in order to fix the issue (including upstream maintainers where relevant);
* credit the reporter in the advisory unless they prefer to remain anonymous;
* tell the reporter when the fix is released and the issue is disclosed.

We may close reports that appear to be unverified automated output without a detailed response.

Double Open does not currently run a bug bounty program and does not pay for reports.

## 6. Conditions for reporters

Research is covered by this policy only if you:

* report the issue to us promptly and through the channels in section 4, and to no one else until it is publicly disclosed under section 9 or 90 days have passed since acknowledgment, whichever is earlier;
* limit testing to what is needed to demonstrate the issue.
  Do not exploit it further, do not use it to gain or keep access, and do not change or delete data;
* stop and report immediately if you encounter personal data, customer data, credentials, or other confidential information.
  Do not copy or keep it, delete anything already retrieved, and confirm deletion on request.
  Treat such information as confidential permanently;
* do not use the vulnerability or anything learned through it for any purpose other than reporting it to us;
* do not degrade availability of services, do not run automated or high-volume tests against our services, and do not use social engineering, phishing, or physical attacks;
* test only against systems operated by Double Open, never against customers' installations without their written permission;
* do not demand payment or other consideration as a condition of reporting or of withholding publication;
* verify the issue yourself before reporting.
  Reports written or generated with AI tools are welcome if a person has reproduced the issue and can answer questions about it.
  Say in the report which tools were used.
  Reports that show no human verification, or that describe an issue that cannot be reproduced from the information given, may be closed without further analysis, and repeated submissions of that kind will not be answered;
* comply with applicable law.

## 7. Safe harbor

Research that complies with section 6 is authorized by Double Open.
We will not pursue or support legal action against you for such research, and we will not refer it to law enforcement.
If a third party initiates action against you for research that complied with this policy, we will confirm that it was authorized.
We will assess compliance reasonably and in good faith.
This authorization binds Double Open only; it does not extend to customers, upstream projects, or service providers whose systems may be affected.
If you are unsure whether something is covered, ask us before proceeding.

## 8. Handling process

1. **Receipt**: the coordinator acknowledges the report and records it in a private GitHub security advisory in the affected repository (or in the internal tracker for services and infrastructure).
2. **Triage**: the Security Team confirms the issue, assesses severity using CVSS v3.1 or later, and identifies affected versions and components.
3. **Fix**: maintainers develop the fix in the advisory's private fork or in a private branch.
   Fixes for hosted services are deployed as soon as they are ready, independent of disclosure timing.
4. **Upstream coordination**: if the issue is in, or also affects, an upstream project, the Security Team notifies that project's security contact and aligns timing with them.
5. **Release**: the fix is released through the project's normal release channel.
6. **Disclosure**: the advisory is published on GitHub, a CVE is requested through GitHub's CNA where the issue merits one, and affected customers are notified under their contracts.

Resolution may also consist of a documented workaround or a risk analysis concluding that no fix is needed; the reporter is informed in either case.

## 9. Disclosure

Public disclosure normally consists of:

* a GitHub security advisory in the affected repository,
* a CVE record where applicable,
* release notes for the fixed version.

Where a vulnerability affects only a Double Open operated service and no customer action is required, disclosure may be limited to a notice to affected customers.

## 10. Supported versions

Unless a repository states otherwise, security fixes are provided for the latest release and the default branch only.
Hosted services are always updated to the fixed version.

## 11. Contact

security@doubleopen.io

## 12. Changes to this policy

This policy is maintained in the [doubleopen-io/.github](https://github.com/doubleopen-io/.github) repository.
Changes are made by pull request and reviewed by the Security Team.
