# n8n Workflows

A collection of automated workflows built with n8n for content creation and marketing automation.

## Overview

This repository contains n8n workflows designed to automate various content creation and marketing tasks using AI and automation tools. Each workflow is ready to import into your n8n instance.

## Workflows

| Workflow Name                                                         | Description                                                                                                  | Trigger                                          | Key Features                                                                                                                                                                            |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Generate UGC marketing videos for eCommerce with VLM Run, Open Ai** | Automatically generates authentic User-Generated Content (UGC) style marketing videos for eCommerce products | Form submission (Product image + Product name)   | • AI-powered product analysis<br>• Influencer persona creation<br>• Multiple video script generation<br>• Video generation with VLM Run<br>• Automatic Google Drive upload              |
| **Write a WordPress post with AI (starting from a few keywords)**     | Creates complete WordPress blog posts from keywords, including content, structure, and featured images       | Form submission (Keywords, chapters, word count) | • SEO-friendly article generation<br>• Wikipedia integration for accuracy<br>• Multi-chapter content creation<br>• AI-generated featured images<br>• Automatic WordPress draft creation |

## Getting Started

### Prerequisites

- An n8n instance (self-hosted or cloud)
- API credentials for the services used in each workflow:
  - **OpenAI API** (for AI content generation)
  - **VLM Run API** (for video and image generation)
  - **Google Drive** (for video storage - first workflow)
  - **WordPress** (for blog post publishing - second workflow)

### Installation

1. Clone or download this repository
2. Import the workflow JSON files into your n8n instance:
   - Go to your n8n dashboard
   - Click "Workflows" → "Import from File"
   - Select the desired workflow JSON file from the `workflows/` directory
3. Configure credentials in n8n:
   - Set up your OpenAI API credentials
   - Set up your VLM Run API credentials
   - Configure Google Drive credentials (for video workflow)
   - Configure WordPress credentials (for blog post workflow)
4. Update workflow settings:
   - Adjust any hardcoded URLs or paths
   - Configure form trigger URLs if needed
   - Set up Google Drive folder paths (first workflow)
   - Set WordPress URL (second workflow)

### Usage

#### Generate UGC Marketing Videos

1. Access the form trigger URL provided by n8n
2. Upload a product image
3. Enter the product name
4. Submit the form
5. Wait for the workflow to complete (video generation may take several minutes)
6. Find your generated videos in the configured Google Drive folder

#### Create WordPress Posts

1. Access the form trigger URL provided by n8n
2. Enter comma-separated keywords for your article
3. Select the number of chapters (1-10)
4. Specify the maximum word count
5. Submit the form
6. The workflow will create a draft post on your WordPress site with:
   - SEO-optimized title and subtitle
   - Structured content with multiple chapters
   - AI-generated featured image

## Workflow Details

### Generate UGC Marketing Videos

This workflow automates the creation of authentic-looking UGC marketing videos:

1. **Product Analysis**: Uses VLM vision model to analyze the product image
2. **Persona Creation**: Generates a detailed influencer profile suited for the product
3. **Script Generation**: Creates multiple 12-second UGC video scripts with frame-by-frame breakdowns
4. **Frame Generation**: Adapts product images to UGC aesthetic and aspect ratio
5. **Video Production**: Generates videos using VLM Run API
6. **Upload**: Automatically uploads completed videos to Google Drive

**Output**: Multiple video variations (720x1280 format) optimized for social media

### Write WordPress Posts

This workflow creates complete blog posts from simple keywords:

1. **Structure Creation**: Generates article title, subtitle, introduction, conclusions, and chapter outlines
2. **Content Generation**: Writes detailed content for each chapter using Wikipedia for accuracy
3. **Image Generation**: Creates a featured image using VLM Run
4. **WordPress Publishing**: Posts the article as a draft with the featured image attached

**Output**: Complete WordPress draft post ready for review and publishing

## Requirements

### For Video Generation Workflow

- OpenAI API account with GPT-4 Turbo access
- VLM Run API account
- Google Drive account
- Sufficient API credits for video generation

### For WordPress Post Workflow

- OpenAI API account with GPT-4o-mini or higher
- VLM Run API account
- WordPress site with REST API enabled
- WordPress API credentials (Application Password)

## Customization

Both workflows can be customized to fit your specific needs:

- **Video duration**: Adjust in the video generation node
- **Article length**: Configure word count and chapter numbers
- **Output formats**: Modify aspect ratios, image sizes, etc.
- **Storage locations**: Change Google Drive folders or WordPress settings
- **AI models**: Switch between different OpenAI models as needed

## Notes

- Video generation can take several minutes per video depending on API response times
- Ensure you have sufficient API credits before running workflows
- WordPress posts are created as drafts - review before publishing
- All workflows include error handling and data validation

## Support

For issues or questions:

- Check n8n documentation: https://docs.n8n.io
- Review workflow node configurations
- Verify API credentials and permissions

## License

This repository contains workflow templates for use with n8n. Ensure compliance with all API terms of service and usage policies.
