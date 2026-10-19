# Wireshark: Videos, Books, Captures, and Case Studies

<a href="https://www.wireshark.org/learn.html"><img src="../assets/tool-wireshark.svg" alt="Wireshark learning resources" width="56" height="56"/></a>

Find a teacher, a capture to examine, or an investigation to follow. If packet analysis is new to you, begin with the learning page and a saved capture before capturing live traffic.

[Watch](#watch-and-understand) · [Read](#read-and-explore) · [Practise](#try-it-yourself) · [Case studies](#see-it-used) · [Further discoveries](#worth-discovering)

## Start with these

| You want to… | Open |
| --- | --- |
| Find installation and first-capture guidance | [Wireshark Learn](https://www.wireshark.org/learn.html) — the project’s starting point, including filters and training directions. **Free guides; linked training has separate terms.** |
| Learn from a structured reading sample | [Working with Captured Packets](https://nostarch.com/download/PPA3_Ch4.pdf) — Chris Sanders’s sample chapter on navigating captures, timing, and filters. **Free PDF · Older interface examples.** |
| Examine traffic without a live capture | [Wireshark sample captures](https://www.wireshark.org/resources) — choose a described capture matching a protocol you understand. **Free downloads · Wireshark needed.** |

## Watch and understand

**[Chris Greer’s YouTube channel →](https://www.youtube.com/@ChrisGreer)**  
Discover packet-analysis teaching from the instructor linked on Wireshark’s learning page. Choose an introductory explanation before a specialist investigation. **YouTube channel · Public videos; external courses have separate access.**

**[Introduction to Wireshark: Making Sense of the Matrix →](https://sharkfest.wireshark.org/retrospective/sfus/sf15us/)**  
Find Chris Greer’s session 02 in the 2015 Tuesday classes, with its presentation and video link. Use it for an introduction; compare interface details with the current guide. **Conference session · Archived material.**

## Read and explore

**[Practical Packet Analysis, 3rd Edition →](https://nostarch.com/packetanalysis3)**  
Chris Sanders, No Starch Press. Choose this for a book-length route through protocols, troubleshooting, and packet interpretation. **Paid book · Free sample chapter · Based on Wireshark 2.x.**

**[Display Filter Reference →](https://www.wireshark.org/docs/dfref/)**  
Look up protocol fields and their supported version ranges when you know what you want to isolate. **Free reference · Use alongside the guide, rather than as a first tutorial.**

## Try it yourself

**[Wireshark’s sample-capture collection →](https://www.wireshark.org/resources)**  
Search the catalog for a protocol you recognize. The `dns+icmp.pcapng.gz` entry is one starting option for examining DNS and ICMP together. **Free capture collection · Local analysis · No cloud account needed.**

**[Practical Packet Analysis companion captures →](https://nostarch.com/packetanalysis3)**  
Use the publisher page’s **Extra Stuff** download to obtain the book’s example captures. Keep the chapter beside the matching file rather than treating the archive as an unlabeled exercise. **Free companion download · The full book is paid.**

For a first exercise, open one saved capture, identify a conversation, and explain the observations supporting your interpretation. Keep the original file unchanged. Captures can contain sensitive data or hostile traffic; use a maintained Wireshark release, do not replay unknown traffic, and capture live traffic only with authorization. Remove downloaded or exported files when you no longer need them.

## See it used

The [SharkFest 2019 US archive](https://sharkfest.wireshark.org/retrospective/sfus/sf19us/) provides presentation and recording links for these specific sessions. Start with one question; older interfaces may differ from yours.

| Your question | Find this session |
| --- | --- |
| How does an analyst approach a slow network? | **21 · Troubleshooting slow networks**, Chris Greer |
| How is packet evidence used in a case study? | **30 · Using Wireshark to solve real problems for real people**, Kary Rogers |
| Can you investigate from the command line? | **04 · Solving (SharkFest) packet capture challenges with only tshark**, Sake Blok |

## Worth discovering

**[SharkFest retrospective library →](https://sharkfest.wireshark.org/retrospective/)**  
Browse conference years and regions to discover speakers, specialist protocols, and analysis techniques beyond introductory videos. **Talk and slide catalog · Recording access and availability vary by session.**

Pick a recording for reasoning, a reference for exact syntax, and a capture for practice. A tutorial’s filter can help you find traffic; you still need to explain what that traffic establishes.

[All tool sources](README.md) · [Learning libraries](../08-learning-libraries/) · [Directory homepage](../README.md)
