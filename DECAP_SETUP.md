# Decap CMS Setup Guide

This guide will help you set up Decap CMS (formerly Netlify CMS) for your website.

## What is Decap CMS?

Decap CMS is a Git-based content management system that allows you to edit content directly in your Git repository. It's perfect for static websites and provides a user-friendly interface for non-technical users.

## Setup Steps

### 1. GitHub OAuth App Setup

1. **Go to GitHub Settings**:
   - Visit [GitHub Settings > Developer settings > OAuth Apps](https://github.com/settings/developers)
   - Click "New OAuth App"

2. **Configure OAuth App**:
   - **Application name**: `Central Website CMS`
   - **Homepage URL**: `https://marvelous-babka-e89623.netlify.app/`
   - **Authorization callback URL**: `https://marvelous-babka-e89623.netlify.app/admin`

3. **Get Credentials**:
   - Copy the **Client ID**
   - Generate a **Client Secret**

### 2. Netlify Environment Variables

1. **Go to Netlify Dashboard**:
   - Visit your site's dashboard on Netlify
   - Go to **Site settings > Environment variables**

2. **Add Variables**:
   - `GITHUB_CLIENT_ID`: Your GitHub OAuth Client ID
   - `GITHUB_CLIENT_SECRET`: Your GitHub OAuth Client Secret

### 3. Update Configuration

Update `admin/config.yml` with your actual GitHub OAuth Client ID:

```yaml
backend:
  name: git-gateway
  branch: main

media_folder: "images/uploads"
public_folder: "/images/uploads"

collections:
  - name: "blog"
    label: "Blog Posts"
    folder: "posts"
    create: true
    slug: "{{year}}-{{month}}-{{day}}-{{slug}}"
    fields:
      - { label: "Title", name: "title", widget: "string" }
      - { label: "Date", name: "date", widget: "datetime" }
      - { label: "Body", name: "body", widget: "markdown" }
      - { label: "Description", name: "description", widget: "text", required: false }
      - { label: "Tags", name: "tags", widget: "list", required: false }
```