#!/bin/bash

# نام ریپو
REPO="git@gitlab.com:Shastay/AI3.git"
BRANCH="add-project-overview-doc"
DOC_PATH="docs/Project_Overview_Shayan_Pirzadeh.md"
LOCAL_REPO="AI3"

# کلون کردن ریپو
git clone "$REPO"
cd "$LOCAL_REPO" || exit

# ساخت شاخه جدید
git checkout -b "$BRANCH"

# اطمینان از وجود پوشه docs
mkdir -p docs

# ایجاد فایل مستند پروژه (Markdown)
cat <<EOF > $DOC_PATH
# 📋 Structured Overview of My Current Projects

**Author**: Shayan Pirzadeh  
**Date**: June 9, 2025

## 🧱 Layer 1: Personal Identity & Core Infrastructure
- Digital Business Card Website (GitHub Pages)
- Aurora E-commerce Template

## 🤖 Layer 2: AI Assistant App
- AI3 Flutter-based Assistant (Chat, Media, Memory)

## 🛠 Layer 3: Internal CI/CD Infrastructure
- Git Server + Jenkins/GitLab Runner + Monitoring

## 🧾 Layer 4: Legal and IP Framework
- Legal Templates (IP, Privacy, Usage Rights)

## 🎨 Layer 5: Visual and UX Design
- Sci-Fi Female AI Character (Emotional variants)

---

Let me know if you'd like more detailed timelines or action plans.

**Best**,  
_Shayan Pirzadeh_
EOF

# افزودن، کامیت و پوش
git add $DOC_PATH
git commit -m "Add structured project overview as Markdown documentation

- Summarizes all active projects with layers and categories
- Details tech stack, purpose, and key features for each project
- Improves team clarity and planning for ongoing work"
git push -u origin "$BRANCH"

echo "✅ Done. Now go to GitLab and create a Merge Request from '$BRANCH' to 'main'."
