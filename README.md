# Google Drive Upload Action

A robust, Python-based GitHub composite action to upload files directly to Google Drive using a Google Service Account. 
Features auto-sharing (Anyone with link can view) and optional Slack notifications.

## Usage

In your project's GitHub Actions workflow file, use this action like so:

```yaml
- name: Upload to Drive
  uses: Webwiders-React/google-drive-upload-action@main
  with:
    credentials_json: ${{ secrets.RAJ_DRIVE_CREDS }}
    folder_id: "1NQ6MDUelMefHghVA_unvsi9YY_sX7wzu"
    file_path: "path/to/your/file.apk"
    
    # (Optional) Send a notification when upload finishes
    slack_webhook_url: ${{ secrets.SLACK_WEBHOOK_URL }} 
```

## Setup Requirements

1. **Service Account Credentials:** 
   You must create a Service Account in Google Cloud, generate a JSON key, and save that exact JSON text as a GitHub Secret (e.g., `RAJ_DRIVE_CREDS`).
2. **Drive Folder Permissions:**
   The Google Drive folder you upload to must be shared with the Service Account email (e.g. `github-actions-uploader@....gserviceaccount.com`) as an **Editor**.
