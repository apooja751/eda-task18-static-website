# Task 18: Host a Simple Static Website Using AWS S3

## 📌 Task Overview

This task demonstrates how to create and deploy a simple static portfolio website using **Amazon Web Services (AWS) S3 Static Website Hosting**.

The website is developed using HTML and CSS and hosted directly from an S3 bucket without managing a web server or virtual machine.

## 🎯 Objectives

- Create a simple static website using HTML and CSS.
- Create and configure an Amazon S3 bucket.
- Upload website files to cloud object storage.
- Enable S3 Static Website Hosting.
- Configure public read access using an S3 bucket policy.
- Access and verify the deployed website through its website endpoint.
- Understand serverless static website hosting.

## 🛠️ Technologies Used

- **AWS S3:** Cloud object storage and static website hosting
- **HTML5:** Website structure and content
- **CSS3:** Website styling and responsive layout
- **GitHub:** Source code management and project documentation


## 📂 Project Structure

```text
veda-task18-static-website/
│
├── index.html
├── style.css
├── README.md
└── screenshots/
    ├── Task18_01_Local_Website_Preview.png
    ├── Task18_02_Local_Website_Sections.png
    ├── Task18_03_Bucket_Configuration.png
    ├── Task18_04_Bucket_Created.png
    ├── Task18_05_Upload_Files_Review.png
    ├── Task18_06_Files_Uploaded.png
    ├── Task18_07_Static_Hosting_Configuration.png
    ├── Task18_08_Static_Hosting_Enabled.png
    ├── Task18_09_Bucket_Policy_Saved.png
    ├── Task18_10_Website_Endpoint.png
    └── Task18_11_Live_Website.png
```

## 💻 Website Features

- Portfolio-style landing page
- Introduction and About Me section
- Technical skills section
- Contact section with a GitHub profile link
- Responsive layout for different screen sizes
- Custom styling using CSS

## ⚙️ AWS Configuration

|   Configuration   |         Details             |
|-------------------|-----------------------------|
| AWS Service       | Amazon S3                   |
| AWS Region        | Asia Pacific (Mumbai)       |
| Region Code       | `ap-south-1`                |
| Bucket Name       |`task18-static-website`      |
| Hosting Type      | Static website hosting      |
| Index Document    | `index.html`                |
| Error Document    | Not configured              |
| Public Access     | Enabled for website objects |
| Access Permission | `s3:GetObject`              |

## 🚀 Implementation Steps

### Step 1: Create the Website

Created two files:

- `index.html` — Contains the website structure and content.
- `style.css` — Defines the colors, layout, navigation, skills cards, and responsive styling.

### Step 2: Create the S3 Bucket

1. Opened the AWS Management Console.
2. Navigated to Amazon S3.
3. Created the bucket `task18-static-website`.
4. Selected the Mumbai region (`ap-south-1`).
5. Kept the recommended bucket ownership and encryption settings.

### Step 3: Upload Website Files

Uploaded `index.html` and `style.css` directly to the root of the S3 bucket.

Verified that both files were uploaded successfully.

### Step 4: Enable Static Website Hosting

1. Opened the bucket's Properties tab.
2. Located Static website hosting.
3. Enabled hosting for a static website.
4. Set `index.html` as the index document.
5. Saved the configuration.

### Step 5: Configure Public Access

1. Updated the bucket-level Block Public Access settings for this demonstration.
2. Added a bucket policy allowing public read access to website objects.
3. Saved the policy and verified that AWS accepted it.

**Bucket policy used:**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadForStaticWebsite",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::task18-static-website/*"
    }
  ]
}
```

This policy permits public reading of objects in the bucket. It does not grant public upload, modification, or deletion permissions.

### Step 6: Verify the Website

Opened the S3 website endpoint in a browser and verified that:

- The homepage loaded successfully.
- HTML content displayed correctly.
- CSS styling was applied.
- The About Me and Technical Skills sections were visible.
- The GitHub link was available.

## 📸 Screenshots

The `screenshots/` folder contains evidence of the local website, bucket creation, file uploads, static website hosting configuration, bucket policy, website endpoint, and live deployment.

## 🔐 Security Considerations

- Public access is enabled only for this demonstration website.
- The bucket policy grants `s3:GetObject` and does not grant write or delete permissions.
- No private information, access keys, passwords, or confidential files should be uploaded to the public bucket.
- The S3 static website endpoint uses HTTP and does not provide HTTPS by itself.
- For production use, consider CloudFront with HTTPS and keep the S3 bucket private where appropriate.
- After completing the demonstration, disable public access and remove the public-read bucket policy if the website no longer needs to be publicly available.

## 💰 Cost Considerations

Amazon S3 charges may apply depending on storage, requests, data transfer, account eligibility, and applicable free-tier offers.

Monitor AWS billing and remove unused resources after the project if they are no longer required.

## 🔄 Rollback and Cleanup

To remove the public website access:

1. Open the S3 bucket in the AWS Console.
2. Navigate to **Permissions → Bucket policy**.
3. Delete the public-read bucket policy.
4. Return to **Block public access (bucket settings)** and enable all four blocking options.
5. If the project is no longer needed, disable Static website hosting under the Properties tab.
6. Back up any files you want to keep.
7. Empty the bucket and delete it if you no longer need it.

**Important:** The website will stop being publicly accessible after public access is removed. Verify the correct bucket before deleting anything.

## 📚 Learning Outcomes

- Learned how to create and configure an Amazon S3 bucket.
- Understood cloud object storage and static website hosting.
- Practiced uploading and organizing website files in S3.
- Learned how bucket policies control public object access.
- Deployed and tested a live website using a cloud storage service.
- Understood basic security, cost, and cleanup considerations.

## ✅ Result

Successfully created a static portfolio website using HTML and CSS, hosted it on Amazon S3, configured the required website access, and verified the deployed website through its S3 website endpoint.

