# VERIQTA Discovery Writing and Curation Standard

Use this standard when you select, describe, organize, or maintain a resource. Your job is to help someone discover a worthwhile place to learn and decide what to open next.

## 1. Make discovery the purpose

Collect useful teaching websites, YouTube channels, individual videos, playlists, open books, paid books, interactive explanations, labs, talks, engineering articles, and official references. Official documentation is one part of a collection, not its automatic substitute.

A reader should leave with a useful discovery and a reason to explore it. Prefer a specific lesson or session when you can identify one; link an entire catalog when discovering the catalog is the point.

## 2. Choose the right home

| Location | Its responsibility |
| --- | --- |
| `01-start-here/` | Help you choose a browsing route |
| `02-career-paths/` | Map responsibilities to relevant subject and tool collections |
| `03-engineering-topics/` | Collect resources about concepts that span products |
| `04-tools-and-technologies/` | Keep each tool’s videos, websites, books, practice, and case studies together |
| `05-cloud-platforms/` | Organize provider and service-specific discoveries |
| `06-hands-on-practice/` | Help you discover places and collections for practice |
| `07-engineering-in-the-wild/` | Collect real engineering accounts, talks, and investigations |
| `08-learning-libraries/` | Help you discover an entire teacher, channel, publisher, or learning platform |

Keep all content files directly inside their numbered main folder. Do not add subfolders. Keep graphics and their attribution directly inside the flat `assets/` folder. Use descriptive, lowercase, hyphenated filenames.

The tool collection spans DevOps, cloud, SRE, networking, Linux and Windows administration, platform engineering, security, databases, and infrastructure. Create a file when the technology offers a distinct discovery destination, not merely another keyword variation.

## 3. Research beyond the first search results

Look in project learning pages, conference archives, creator websites, university material, book publishers, specialist communities, and practice catalogs. Follow useful references to their original publishers.

Include well-known starting resources alongside overlooked material that adds something distinctive. Do not describe a find as hidden, best, essential, or definitive without a defensible reason. Obscurity and popularity are not evidence of teaching quality.

Compare overlapping candidates. Keep the one that serves the reader better, or explain why two different treatments are useful.

## 4. Inspect what you describe

Open every destination. Confirm the title, author or publisher, relevant content, access conditions, and intended level. Inspect enough of the material to support the description. A search snippet, thumbnail, or channel name does not establish teaching quality.

For videos, inspect the relevant segment or a usable transcript; verify the title and creator. If you can only inspect an event listing, describe the listed session and point to that listing. Do not imply you watched the recording.

Check free-versus-paid access, registration, region restrictions when known, required accounts, infrastructure costs, downloadable material, and important prerequisites. Do not guess. Replace or omit a resource when you cannot establish the information needed to recommend it.

Use official documentation or standards to verify claims about product behavior. A community explanation can be an excellent teaching resource without being the authoritative source for a version-specific limit.

## 5. Make each entry help you choose

Use a clickable title, one specific reason to open it, and the labels that affect the choice.

> **[Resource title →](https://example.com/)**  
> Explain what it teaches particularly well and where you should begin.  
> **Video playlist · Free · Basic networking knowledge helpful**

This is an entry pattern, not a compulsory layout. A table, a short annotated list, or a visual row can work better. Do not repeat five empty fields for every resource.

Identify the author or publisher where it is not obvious. Separate the resource’s format, access, and difficulty. Free documentation does not make a product, cloud deployment, or linked course free. Label a free sample separately from its paid book.

## 6. Adapt the page to the discoveries

Possible sections are **Start with these**, **Watch and understand**, **Read and explore**, **Try it yourself**, **See it used**, and **Worth discovering**. Use only the sections that have worthwhile material. Rename them when a more specific heading helps.

Put a few strong choices near the top. Keep each resource in the section where it adds the most value. A starting table may point to a deeper entry, but should not reproduce that entry’s whole description.

Do not fill missing sections with weak links. Do not turn every page into the same sequence of paragraphs. A packet-analysis page and a cloud-identity page should reflect different learning needs.

## 7. Keep writing concise and human

Address people worldwide as **you** and **your**. Begin with the subject or the question they want answered. Use precise descriptions, restrained adjectives, and familiar language.

Explain the distinction that helps someone choose: a visual introduction, a command reference, a complete course, or an advanced investigation. Avoid generic praise such as “an amazing resource to master everything.”

There is no mandatory word count or resource count. Comprehensive means covering the important discovery needs within the stated scope. Remove repeated introductions, conclusions, tool descriptions, and career advice that does not help resource selection.

## 8. Make visual navigation useful

Use authentic tool marks when available, with readable names and descriptive alternative text. Link each logo and its adjacent name to the same destination. Use plain name tiles when an appropriate logo is unavailable; never invent a replacement brand mark.

Store graphics locally where practical. Preserve logo geometry and record source and license information in `assets/ATTRIBUTION.md`. Use small graphics, sufficient contrast, and text alternatives. Do not place essential navigation solely inside an SVG.

For the homepage, group the large tool table by recognizable engineering tasks. Keep rows compact and avoid long descriptions inside logo cells. Check narrow-screen reading and light and dark themes when changing layout.

## 9. Make practice listings concrete

Briefly explain what you can practise, what environment or prior knowledge you need, access and infrastructure conditions, the result to check, and relevant cleanup. Link to the actual exercise or clearly label a practice catalog.

Do not write a complete tutorial inside every listing. If you include consequential commands, provide the necessary environment, permissions, interpretation, verification, and recovery context. Never invent successful results or claim that VERIQTA executed an exercise without evidence.

For incidents and case studies, preserve the original organization, date, conditions, and uncertainty. Explain why the account is useful without treating its architecture as universally appropriate.

## 10. Publish for readers

Resource pages contain finished public-facing writing. Keep preparation dates, internal research notes, review-scope summaries, generation reports, execution-history disclaimers, and instructions to the writer out of them.

Keep meaningful technical context such as versions, costs, access requirements, limitations, and cleanup. Maintain research evidence separately from published resource prose. Do not invent experience, reviewers, credentials, endorsements, or test results.

A reserved empty file is not an available collection. List it as pending in the file map, and offer working source links or completed collections through the public indexes.

## 11. Connect the library without duplication

Give a tool one primary home. Career pages select and link the relevant tool and topic collections. Learning libraries describe a channel or platform as a whole; subject pages select its relevant individual lessons.

Use relative links for repository navigation and direct HTTPS links for external sources. Use one descriptive H1 and logical headings. Avoid copied descriptions, keyword stuffing, artificial FAQs, arbitrary length targets, and unsupported ranking promises.

## 12. Check before publishing

- You can understand the page’s purpose immediately.
- Useful discoveries appear near the top.
- Each included resource has a clear reason to be there.
- The collection offers appropriate formats and perspectives for its subject.
- Titles, creators, descriptions, access, and prerequisites match the destinations.
- Old interfaces or version-specific material have meaningful context.
- Links, anchors, images, and text alternatives work.
- Shared resources have a clear primary home.
- No empty collection is advertised as finished.
- No filler, repeated paragraphs, unsupported claims, or internal production notes remain.
- Graphic attribution and applicable licenses are preserved.

**The standard: discover carefully, explain the value briefly, and make the next useful resource easy to open.**
