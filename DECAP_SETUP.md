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
   - **Homepage URL**: `https://your-site-name.netlify.app`
   - **Authorization callback URL**: `https://your-site-name.netlify.app/auth`

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
  name: github
  repo: GopalShenoy12/central-website
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

### 4. Deploy

1. **Commit and push your changes**:
   ```bash
   git add .
   git commit -m "Update Decap CMS configuration"
   git push origin main
   ```

2. **Netlify will automatically deploy** the changes

### 5. Access CMS

1. **Visit your CMS**:
   - Go to `https://your-site-name.netlify.app/admin`
   - Click "Login with GitHub"
   - Authorize the application

2. **Start creating content**:
   - Click "New Blog"
   - Fill in the form
   - Click "Publish"

## Features

### Blog Posts
- **Title**: The post title
- **Date**: Publication date
- **Body**: Main content (Markdown supported)
- **Description**: Optional post description
- **Tags**: Optional tags for categorization

### Media Management
- Upload images to `/images/uploads`
- Images are automatically optimized
- Access via `/images/uploads/filename.jpg`

### Markdown Support
The CMS supports full Markdown:
- **Headers**: `# ## ###`
- **Bold**: `**text**`
- **Italic**: `*text*`
- **Links**: `[text](url)`
- **Images**: `![alt](url)`
- **Lists**: `- item` or `1. item`
- **Code**: `` `code` `` or ``` ``` ```

## Troubleshooting

### Common Issues

1. **"Failed to load config"**:
   - Check that `admin/config.yml` is valid YAML
   - Ensure the GitHub repository path is correct

2. **"Authentication failed"**:
   - Verify GitHub OAuth App settings
   - Check environment variables in Netlify
   - Ensure callback URL matches exactly

3. **"Cannot access repository"**:
   - Make sure the GitHub user has access to the repository
   - Check repository permissions

### Getting Help

- [Decap CMS Documentation](https://decapcms.org/docs/)
- [GitHub OAuth Apps](https://docs.github.com/en/developers/apps/building-oauth-apps)
- [Netlify Functions](https://docs.netlify.com/functions/overview/)

## Security Notes

- Keep your GitHub Client Secret secure
- Never commit secrets to your repository
- Use environment variables for sensitive data
- Regularly rotate your OAuth credentials 