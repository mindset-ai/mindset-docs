---
description: File types, size limits, and what we can and can't do.
icon: page
---

# Supported Files

We currently support the following file types for ingestion:

#### 📄 Documents

* Google Docs
* Microsoft Word (.docx)
* PDF (with page breaks)
* Plain text (.txt)

#### 📊 Presentations

* Google Slides
* Microsoft PowerPoint (.pptx)

#### 🎵 Audio

* MP3

#### 🎥 Video

* MP4

🖼️ _Images embedded within supported document and presentation files will also be ingested._

***

### File Size Limits

* **Google Docs & Google Slides**:\
  Subject to Google’s hard limit of **15MB**.
* **DOCX & PPTX files**:\
  Recommended maximum size is **70MB**. Larger files may be ingested, but performance can vary depending on document complexity and length.\
  ⚠️ _Large, image-heavy PowerPoints may time out during processing._
* **Video & Audio files**:\
  We typically support files up to **1GB**, though we’ve occasionally been able to process larger files. However, stability and success are not guaranteed above this limit.\
  ⏳ _Duration is less important than file size—we’ve ingested files several hours long._

***

### Unsupported Content

We currently do **not** support:

* **PDFs without page breaks**\
  (e.g. a single, unbroken stream of content or an image-based PDF)
* **Tabular-only documents**\
  (e.g. a PDF or DOCX that consists mainly of a large, continuous table)
* **Videos without audio**\
  (e.g. silent screen recordings)
* **Text displayed during a Video**



