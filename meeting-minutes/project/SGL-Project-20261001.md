![logo](logo_elisa_small.png )

## ELISA Space Grade Linux Special Interests Group

The goal of the group is to advance space technology innovation and competitiveness by developing a common Linux distribution that can be used in space applications, ready for the challenges of deep space, often long lifespan robotic or human-based missions. The nature of space missions brings many challenges, from development to deployment there are multiple considerations that need to be considered. Furthermore this group is the initial step towards creating an ecosystem of supported platforms and a community that benefits from them, and also from the open source nature of the project. (https://lists.elisa.tech/g/space-grade-linux/)

# Minutes

## 1 October, 2026

---

# Agenda

- Roll Call
- Brief Notices
- Announcements
  - Upcoming Events
  - Project news
- Main Topic: RFC review (five RFCs in Draft)
  - How the RFC process works
  - RFC-0001: Software-defined vehicle architecture for space systems
  - RFC-0002: Radiation fault injection in CI
  - RFC-0003: Hardware-in-the-loop testing in CI
  - RFC-0004: Long-term support releases
  - RFC-0005: Certification baseline for downstream adopters
  - Cross-cutting questions
- Mailing List Highlights
- Action Items Review
- Open Discussion / AOB
- Closing

---

# Roll Call

## Attended this meeting

- Ramón Roche (Dronecode Foundation)
- Matt Weber (The Boeing Company)
- Piotr Skrzypek (European Space Agency)
- Yasushi SHOJI (Space Cubics)
- Nick Zajerko-McKee (Vorago Technologies)
- Subhajit Ghosh (Tweaklogic)
- Leonidas Kosmidis (Barcelona Supercomputing Center)
- Philip Balister (OpenEmbedded)
- Gary Crum (Voyager Technologies)
- Haoda Wang "Harry" (Columbia University)
- Xavier Scholtes (SES)
- Giacomo Forresu (SES)
- Nicolae Butnari (SES)
- Cuauhtemoc Castellanos (SES)
- Cyril Jean (Microchip)
- Alexey Simonov (TII)
- Ivan Perez (KBR @ NASA Ames Research Center)
- Eoin Dickson (Microchip)
- Hiroki Hihara (NEC Space Technologies)


## Attended recently in the past

- Brennan Hay (NASA GSFC)
- Brian Kempa
- Christopher Heistand
- Cyril Jean (Microchip)
- Dongshik Won (TelePIX, KAIST)
- Dhruv Sharma
- Douglas Landgraf (Red Hat)
- Eoin Dickson (Microchip)
- Gabriele Paoloni (Red Hat)
- Hans Weggeman (Wind River)
- Hugo Cornelis (Mind OSS)
- Ivan Perez (KBR @ NASA Ames Research Center)
- Ivan Pravdin (NVIDIA)
- Jan-Simon Moeller (AGL)
- Jan Vermaete
- Joe Speed (Ampere)
- Juan Solano
- Kate Stewart (LF)
- Lukas Mazl (Technical University of Liberec)
- Maciej Nowak (KP Labs)
- Manuel Beltran (Boeing)
- Martin Halle (TUHH)
- Matt Weber (The Boeing Company)
- Michael Krasnyk (The Exploration Company)
- Michael Mahoney (Wind River)
- Michael Monaghan (NASA GSFC)
- Michael Starch (JPL)
- Naga (Timesys/Lynx)
- Naoto Yamaguchi (AISIN)
- Nick Zajerko-McKee (Vorago Technologies)
- Panos Kalorog (NRB)
- Paul Greenwood (Vorago Technologies)
- Pawel Wodnicki (32bitmicro)
- Pedro Roque (Caltech)
- Philip Balister (OpenEmbedded)
- Rahn Twitchell (Tuxera)
- Rob Woolley (Wind River)
- Ryo Takakura
- Sandipan Ghosh (Tweaklogic)
- Shefali Sharma
- Subhajit Ghosh (Tweaklogic)
- Tim Bird (Sony)
- Tony James (Red Hat)
- Tyler Kwolek
- Yasushi SHOJI (Space Cubics)
- Hiroki Hihara (NEC Space Technologies)

---

# Brief Notices

## Code of Conduct and Legal Notices

- ELISA Project meetings involve participation by industry competitors, and it is the intention of the Linux Foundation to conduct all of its activities in accordance with applicable antitrust and competition laws. It is therefore extremely important that attendees adhere to meeting agendas, and be aware of, and not participate in, any activities that are prohibited under applicable US state, federal, or foreign antitrust and competition laws.
  - [Linux Foundation Antitrust Policy](http://www.linuxfoundation.org/antitrust-policy)
- Email communication will be treated as documentation and be received and made available by the Project under the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0). Please refer to the ELISA Technical Charter section 7 subsection iv. for details.
- The discussions in these meetings are exploratory. The opinions expressed by participants are not necessarily the policy of the companies.
- No recordings of working group meetings are permitted. Special provisions may be arranged for recording in advance with explicit consent of the participants.
- The kernel and LF Code of Conduct applies to all communication with this project
  - [Linux Foundation Code of Conduct](https://www.linuxfoundation.org/code-of-conduct/)
  - Linux [Contributor Covenant Code of Conduct](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/Documentation/process/code-of-conduct.rst)
  - Linux Kernel Contributor Covenant [Code of Conduct Interpretation](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/Documentation/process/code-of-conduct-interpretation.rst)

---

# Announcements

## Upcoming Events

- **Oct 6-8** Open Source Summit EU in Prague -> [link](https://events.linuxfoundation.org/open-source-summit-europe/)
- **Oct 7** PX4 After Party at OSS -> [link](https://luma.com/l3vd0qth)
- **Oct 13** High Integrity Systems Conference -> [link](https://www.his-conference.co.uk/)
- **replace date** NASA SPARK -> [link](https://spark.nasa.gov/)

## Project news

- New home for governance: the [space-grade-linux/TSC](https://github.com/space-grade-linux/TSC) repository now holds the [Technical Charter](../../CHARTER.md), the [RFC process](../../rfcs/README.md) and these minutes. Project meeting minutes from January 2025 to August 2026 were imported from elisa-tech/sig-sgl with their history.
- meta-sgl moved from elisa-tech to [space-grade-linux/meta-sgl](https://github.com/space-grade-linux/meta-sgl).

---

# Main Topic: RFC review

Five RFCs were opened as Draft pull requests on September 23 and 24, 2026. This is their first project meeting.

## How the RFC process works

- An RFC is required when a proposal affects more than one part of SGL, creates or changes a working group, or sets a norm the project is held to ([rfcs/README.md](../../rfcs/README.md)).
- Draft comment period: at least two project meetings or three weeks, whichever is longer. Every RFC in Draft is on the agenda of every project meeting.
- Comment inline on the pull request, use GitHub suggestions for exact wording, or reply on the mailing list. The author summarizes list replies on the pull request.
- The TSC decides by consensus first, or by a vote under charter section 3. Accepting an RFC approves a technical direction only; RFCs do not cover resourcing.
- Every RFC proposes a working group that holds its first meeting in Q1 2027, elects its chair (confirmed by the TSC), and reports to the TSC quarterly.

| RFC | Title | Proposed WG | Discussion |
| --- | --- | --- | --- |
| 0001 | Software-defined vehicle architecture for space systems | SDV for Space Architecture WG | [#1](https://github.com/space-grade-linux/TSC/pull/1) |
| 0002 | Radiation fault injection in CI | CI Testing WG | [#2](https://github.com/space-grade-linux/TSC/pull/2) |
| 0003 | Hardware-in-the-loop testing in CI | CI Testing WG | [#3](https://github.com/space-grade-linux/TSC/pull/3) |
| 0004 | Long-term support releases | LTS and Release Engineering WG | [#4](https://github.com/space-grade-linux/TSC/pull/4) |
| 0005 | Certification baseline for downstream adopters | Assurance and Certification WG | [#5](https://github.com/space-grade-linux/TSC/pull/5) |

## RFC-0001: Software-defined vehicle architecture for space systems

[PR #1](https://github.com/space-grade-linux/TSC/pull/1)

**What it proposes:** an open reference architecture for software-defined space vehicles, defined by domain roles and the interfaces between them, not tied to any one OS, hypervisor or board. Domains may run Linux, another general-purpose OS, or an RTOS (Zephyr, TRON, RTEMS, FreeRTOS). A role-level sketch adapted from AGL SoDeV seeds architecture v0.1: guest domains (mission, AI/ML, comms, payload), hard real-time domains, a control domain for lifecycle and FDIR supervision, driver domains, and a flight-critical MCU outside the hypervisor.

**Why:** AGL SoDeV, SOAFEE, the Boeing and AMD Xen FuSa work, and CNES KOSMOS planning a Yocto Linux partition. 16 of 46 survey respondents already use a hypervisor.

**Decision requested:**
1. Charter the SDV for Space Architecture WG (charter 2.g.iv).
2. Adopt the role-level sketch as the seed of architecture v0.1, not as the answer.
3. Authorize the WG to propose liaisons (charter 2.g.v), each confirmed by the TSC.

**Questions for discussion:**
- Are the roles in the sketch the right starting set? Is FDIR supervision in the control domain the right split?
- Which communities should be the first liaisons (AGL, SOAFEE, Xen, Zephyr, OASIS VIRTIO)?
- Who wants to take part in the WG?

**Discussion so far on the PR:** none.

**Notes:**

-

## RFC-0002: Radiation fault injection in CI

[PR #2](https://github.com/space-grade-linux/TSC/pull/2)

**What it proposes:** the CI Testing WG evaluates existing fault injection tools and recommends how SGL CI runs fault injection against SGL images, with results published per release. That includes whether to adopt one tool, with its authors' agreement, as a project hosted by SGL.

**Why:** four independently built QEMU fault injectors are known to the project (Radshield's qemu-hce, the University of Luxembourg SnT plugin, MIT Hailburst, and the EPAM TCG plugin series on qemu-devel), plus BYU SHREC hardware fault injection on Versal. SGL CI runs none of them. Contributors offered time in April 2026 and the proposed working session never happened.

**Decision requested:**
1. Charter the CI Testing WG (charter 2.g.iv) to bring fault injection into SGL CI.
2. Ask it for a recommendation, including whether to adopt a tool. Adoption, and any license exception under charter 7.c (QEMU forks and plugins are GPL), needs a separate TSC decision.

**Questions for discussion:**
- Which fault models first: memory (DRAM, caches, ECC/scrubbing), watchdog recovery, boot?
- Track upstream QEMU (the EPAM series) or run forks in CI meanwhile?
- What metrics should a result contain? The Radshield team asked for input on this.

**Discussion so far on the PR:** none.

**Notes:**

-

## RFC-0003: Hardware-in-the-loop testing in CI

[PR #3](https://github.com/space-grade-linux/TSC/pull/3)

**What it proposes:** SGL images boot and are tested on real boards as part of SGL CI, owned by the CI Testing WG. The WG recommends the boards, hosting, scheduling, tests, access model, handling of donated and export-controlled hardware, and how results are published. Requirement: no use of the boards blocks upstream SGL work.

**Why:** meta-sgl CI builds for three QEMU machines plus BeagleV-Fire and PIC64-HPSC but boots nothing. "CI all the way to hardware" has been an unowned roadmap action item since April 2026. Radiation test failures (BYU SHREC on Versal, SnT on i.MX 8M) and Tuxera's power-interruption questions need real boards. Both boards built today are RISC-V while 83 percent of respondents need ARM.

**Decision requested:**
1. Charter the CI Testing WG (charter 2.g.iv) to bring hardware-in-the-loop testing into SGL CI.
2. Ask it for a recommendation covering at least boards, hosting and access, which comes back to the TSC for approval.

**Questions for discussion:**
- First boards: BeagleV-Fire and PIC64-HPSC, plus an ARM target (Space Cubics offered a Versal-based board)?
- Lab tooling: LAVA, Labgrid, KernelCI-style labs, the Yocto Project lab?
- One hosting site or several?

**Discussion so far on the PR:**
- Philip Balister offered to share his GitLab CI and Labgrid setup for hardware-in-the-loop testing of SGL and GNU Radio.

**Notes:**

-

## RFC-0004: Long-term support releases

[PR #4](https://github.com/space-grade-linux/TSC/pull/4)

**What it proposes:** an LTS and Release Engineering WG that recommends an SGL long-term support policy: what an SGL LTS release contains, reproducibility, cadence and relation to Yocto LTS, the first base (Scarthgap today, Wrynose arriving), support window including a possible CIP SLTS-aligned extended tier, coverage per board, end-of-support notice, and retained test evidence. The author's starting view is that SGL LTS tracks Yocto LTS.

**Why:** Yocto supports an LTS for four years; 59 percent of survey respondents operate systems for five years or more and 33 percent for ten or more. Kirkstone was dropped and Wrynose is arriving with no written policy telling adopters how long a series is supported.

**Decision requested:**
1. Charter the LTS and Release Engineering WG (charter 2.g.iv).
2. Ask it to recommend an SGL LTS policy, which the TSC approves under charter 2.g.vi.

**Questions for discussion:**
- Is a window beyond Yocto's four years realistic, and what maintenance does it take?
- What makes up a release: kas lockfiles, SBOMs, mirrored sources, signed artifacts?
- Ties to the open action item on Wrynose in SGL CI.

**Discussion so far on the PR:** none.

**Notes:**

-

## RFC-0005: Certification baseline for downstream adopters

[PR #5](https://github.com/space-grade-linux/TSC/pull/5)

**What it proposes:** an Assurance and Certification WG that recommends what SGL provides to adopters who certify products built on it, which standards to address first and at which rigor levels, and the project's position on certification of the distribution itself. It also covers ELISA methods and a possible safety manual, safety profiles, a worked example with an adopter, partitioned systems, contributor provenance, flight lessons learned, and keeping all of it current. The author's starting view is that an open source community cannot certify a distribution for a mission, but can build the inputs adopters need once, in the open.

**Why:** repeated asks for ECSS guidance from KP Labs, ESA and CNES, plus Tuxera's question on assurance artifacts. Survey respondents must conform with DO-178 (28 percent), NASA-STD-8739.8, NASA-STD-8719.13 and ISO 26262 (20 percent each), with ECSS appearing as write-ins.

**Decision requested:**
1. Charter the Assurance and Certification WG (charter 2.g.iv).
2. Ask it to recommend what the project provides, which standards come first, and the project's position on certifying the distribution.

**Questions for discussion:**
- ECSS first, DO-178C first, or a common core that carries over?
- Would an adopter volunteer for a worked example?
- How does this coordinate with the ELISA Aerospace WG and the Minimal System Layer roadmap item?

**Discussion so far on the PR:** none.

**Notes:**

-

## Cross-cutting questions

- RFC-0002 and RFC-0003 both charter the CI Testing WG. If both are accepted, the TSC charters one WG with both scopes.
- RFC-0002, 0003, 0004 and 0005 all ask for published evidence (fault injection results, hardware test results, LTS test evidence, certification inputs). The WGs should agree on one place and format for it.
- Five new WGs, all starting in Q1 2027. Is there enough participation to staff all of them, or should some start later?
- The RFC branches still link to elisa-tech/meta-sgl and need updating to space-grade-linux/meta-sgl before merge.
- Timeline: the comment period runs at least until October 15, 2026 (three weeks from the September 24 PRs) and through the next project meeting. The earliest TSC decision is after that meeting.

---

# Mailing List Highlights

-

---

# Action Items Review (from Aug 20)

No minutes were recorded for September 17, so items carry over from August 20.

- Rob Woolley: integrate the new Yocto LTS release (Wrynose) into SGL CI
- Ramón: follow up with Matt Weber on adding a Space workload example to the roadmap
- Group: evaluate FTRFS and ZFS for SGL inclusion, including licensing implications and hardware fault-tolerance baseline assumptions
- Ramón: chase remaining doc relicensing approvals (CC-BY-SA-4.0 -> CC-BY-4.0) from Matthias Schmitz and Celeste
- Roadmap: draft Minimal System Layer proposal, documenting what's in the build and why (related: RFC-0005)
- Roadmap: scope partition stress/analysis work using stress-ng (related: RFC-0003)
- Roadmap: define plan for CI all the way to hardware, verify builds run on target (now proposed in RFC-0003)

---

# Open Discussion / AOB

- Aerospace WG - [PR on Minimizing the Linux Kernel](https://github.com/elisa-tech/wg-aerospace/pull/257/changes)
  - **We need your feedback!**
  - PR covers taking metrics, example measurements, minimizing userspace+kernel, and understanding dead code.
  - Goal: add to <https://docs.kernel.org/>

---

# Closing

## Action Items

- All: review and comment on RFC-0001 to RFC-0005 on their pull requests or on the mailing list
- Ramón: summarize mailing list replies on each RFC pull request
- Ramón: update meta-sgl links in the RFC branches to space-grade-linux/meta-sgl
- Philip Balister: share GitLab CI and Labgrid hardware-in-the-loop setup (RFC-0003)
- Volunteers for each proposed WG: add your name on the RFC pull request

Tracked in [GitHub Issues](https://github.com/space-grade-linux/TSC/issues)

## Next Meeting

- TBD
