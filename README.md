# Project-Datalake2025

> 🚀 **Data Lake Architecture with S3, Glue, and Lake Formation queried via Athena and QuickSight.**

This project demonstrates a scalable and secure architecture for building a data lake on AWS, with a Hugo-based static website to document the design and implementation process.

---

## 📁 Project Structure
.
├── archetypes/ # Hugo archetypes
├── content/ # Workshop content (markdown)
│ ├── 1-Introduce/
│ ├── 2-Prerequisite/
│ └── ... more sections
├── config.toml # Hugo site configuration
├── static/ # Optional: images, diagrams, assets
└── README.md # Project overview

---

## 🧰 Technologies Used

| Layer         | Services/Tools                        |
|---------------|----------------------------------------|
| 🚀 Storage     | Amazon S3                              |
| 🧠 Catalog      | AWS Glue, Lake Formation               |
| 🔎 Query        | Amazon Athena                          |
| 📊 Visualization | Amazon QuickSight                      |
| 🌐 Documentation | Hugo Static Site Generator              |

---

## 🛠️ Getting Started (Local Preview)

Install [Hugo](https://gohugo.io/getting-started/install/) and run:

```bash
hugo server

---
Then open http://localhost:1313 to view the workshop locally.

## ☁️ Deployment (Optional)

You can deploy this Hugo site to AWS S3 + CloudFront with enhanced security and caching:

- S3 static website hosting
- CloudFront with OAI or OAC
- Signed URLs, field-level encryption, Lambda@Edge headers
- CI/CD via GitHub Actions

> 📝 Deployment to S3/CloudFront planned in next steps.

🙌 Author
Project maintained by bamboo7497-fcj as part of an internship project on AWS Data Lake Architecture.