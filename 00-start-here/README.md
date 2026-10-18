# Start Here: Find Engineering Resources That Fit Your Work

Use the VERIQTA Engineering Resource Directory to find references for the engineering task in front of you. You can enter through a career, a technical subject, a tool, a cloud provider, or a production symptom. Choose the route that gets you to useful material with the fewest unnecessary steps.

You do not need to study every collection. A beginner learning Linux, an engineer investigating failed deployments, and an architect comparing recovery options need different starting points.

## Choose the guide you need

| Your situation | Open this guide | What you will leave with |
| --- | --- | --- |
| You are unsure where to begin | [Choose your starting point](choose-your-starting-point.md) | A route based on your existing knowledge and immediate goal |
| You know the subject but cannot locate the right material | [How to find a resource](how-to-find-a-resource.md) | A repeatable way to search and narrow a collection |
| You have several resources and need to choose | [How to evaluate an engineering resource](how-to-evaluate-an-engineering-resource.md) | A way to assess authority, relevance, evidence, and access |
| You want to turn reading into practical work | [How to use learning and production resources](how-to-use-learning-and-production-resources.md) | A process for practice, evidence, adaptation, and verification |

## Understand the directory

The collections provide different views of engineering work. A career connects responsibilities to knowledge. A domain explains a subject. A tool collection helps you work with a particular implementation. A production problem starts from observed behavior.

| Collection | Use it when you need to… |
| --- | --- |
| [Career paths](../01-career-paths/README.md) | Identify resources relevant to a role or responsibility |
| [Engineering domains](../02-engineering-domains/README.md) | Find foundations and deeper subject references |
| [Tools and ecosystems](../03-tools-and-ecosystems/README.md) | Locate implementation documentation and operating resources |
| [Cloud and infrastructure](../04-cloud-and-infrastructure/README.md) | Find provider-specific and infrastructure references |
| [Production problems](../05-production-problems/README.md) | Organize research around a symptom or failure |
| [Learning and practice](../06-learning-and-practice/README.md) | Discover exercises, books, courses, and project resources |
| [Architecture and reliability](../07-architecture-and-reliability/README.md) | Compare designs, resilience approaches, and incident lessons |
| [Standards and documentation](../08-standards-and-documentation/README.md) | Find specifications, frameworks, and authoritative references |
| [Resource indexes](../09-resource-indexes/README.md) | Browse through alternative categories and discovery routes |
| [Contributing and maintenance](../10-contributing-and-maintenance/README.md) | Suggest resources and understand review practices |

**Collection availability:** The directory is being expanded. Several collections currently contain navigation pages whose linked subject files are empty. Those files are unfinished, not available guides. If you reach one, return to its collection or use the external starting resources below. A folder name alone does not establish content availability.

## Start with a question you can answer

Replace a broad intention such as “learn DevOps” with a concrete question:

- How does a process receive configuration and write logs?
- How does a request reach an application through DNS, a network connection, and a service?
- How can you reproduce an infrastructure change and inspect its effects?
- What evidence would show that a failed service has recovered?

Choose one question, identify the knowledge it requires, then select a resource that addresses it. This keeps reading connected to a result you can explain or demonstrate.

For example, if you want to containerize an application, begin with container concepts and a guided workflow. If the application already runs but cannot be reached, begin with its observed behavior and networking references. Both tasks involve containers, but they call for different material.

## Useful external starting resources

These links provide entry points while you explore the directory. Select the sections relevant to your task; none is a complete curriculum for every engineering role.

### [Pro Git, second edition](https://git-scm.com/book/en/v2)

Scott Chacon and Ben Straub's book is freely readable on the Git website. Use it to build an understanding of version control and Git workflows.

- **Best for:** Readers learning Git or revisiting concepts behind everyday commands.
- **Start with:** Getting Started and Git Basics; continue to Git Branching when collaboration requires it.
- **Access:** Free online reading. Local practice requires Git.
- **Important limit:** Git knowledge does not cover every hosting platform's permissions, automation, or review features.

### [Docker Get Started](https://docs.docker.com/get-started/)

Docker's documentation organizes introductory concepts and guided container workflows.

- **Best for:** Readers with basic command-line familiarity who want to understand and run containerized applications.
- **Start with:** The introductory material, then the linked workshop when you have a suitable local environment.
- **Access:** Documentation is publicly readable. Check software licensing and any hosted-service conditions separately.
- **Important limit:** A local container exercise does not establish a production operating model.

### [Kubernetes documentation](https://kubernetes.io/docs/home/)

The Kubernetes project separates conceptual explanations, tutorials, task guides, and reference material.

- **Best for:** Readers choosing material for a specific Kubernetes question.
- **Start with:** Concepts for understanding; tutorials for guided learning; tasks for a defined operation.
- **Access:** Free documentation. Exercises may require local infrastructure or a cloud account.
- **Important limit:** Match the documentation version and environment to the system you use.

### [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/)

Google's publicly readable workbook connects reliability practices with implementation discussions and case studies.

- **Best for:** Readers familiar with operating services who want to study reliability objectives, monitoring, and incident work.
- **Start with:** The chapter matching your current responsibility; use the table of contents to select it.
- **Access:** Free online reading.
- **Important limit:** Organizational examples need adaptation to your staffing, service needs, and infrastructure.

## What a useful resource should give you

Before committing to a book, course, or lab, check its prerequisites, access requirements, applicable environment, and expected outcome. A paid course can be useful, and an official manual can be difficult to learn from. Judge each against the task you need to complete.

When you finish, keep a small record of what you learned, which source supported it, what you tried, and what remains uncertain. For practical work, include observable results and cleanup evidence. Watching an exercise and completing it are different forms of progress.

## Get help or suggest an improvement

When asking for help, provide your goal, environment, versions, observed behavior, expected behavior, and what you have already checked. Remove secrets and private data from examples.

If a resource is misleading, inaccessible, or misplaced, explain the problem and suggest a correction through the [contribution guide](../CONTRIBUTING.md). A precise correction is more useful than adding another broad link.

[Choose your starting point](choose-your-starting-point.md) · [Return to the directory](../README.md)
