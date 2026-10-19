# Storage and Data Recovery

Look for the relationship between the data path, persistence, and a restore you can verify.

## Understand what must survive

| Open | What you can find | Access |
| --- | --- | --- |
| [UNIX and Linux System Administration Handbook](https://www.admin.com/) | The authors’ site for a broad administration reference; choose relevant chapters and confirm current platform details. | Paid book; author resources |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Select a chapter about objectives, alerts, incidents, or releases rather than reading everything in order. | Free online book |
| [Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/) | Study operating-system concepts with free chapters and associated exercises. | Free online textbook |

## Focused references

**[Ceph architecture →](https://docs.ceph.com/en/latest/architecture/)**  
Connect the selected storage interface with its components and data path.  
**Free reference; deployment requires infrastructure**

**[restic restore guide →](https://restic.readthedocs.io/en/stable/050_restore.html)**  
Study restoration before relying on a repository full of backups.  
**Free guide; use synthetic test data**

## Follow the tools

[Ceph](../04-tools-and-technologies/ceph.md) · [MinIO](../04-tools-and-technologies/minio.md) · [restic](../04-tools-and-technologies/restic.md) · [Velero](../04-tools-and-technologies/velero.md)

## Put one idea to work

Back up synthetic files and restore them into a separate location, then compare their contents. Use the selected guide’s prerequisites and verification steps. Choose an owned or provided learning environment, keep sensitive data out of your notes, and remove the exercise resources when finished.

[Browse this collection](README.md) · [Directory homepage](../README.md)
