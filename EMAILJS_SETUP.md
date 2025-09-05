# EmailJS Setup Guide

## Free Email Notifications for Contact Form

This guide will help you set up **EmailJS** to send email notifications when someone submits the contact form. EmailJS offers a **free tier with 200 emails per month**.

## Step 1: Create EmailJS Account

1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Sign up for a free account
3. Verify your email address

## Step 2: Add Email Service

1. In your EmailJS dashboard, go to **"Email Services"**
2. Click **"Add New Service"**
3. Choose **Gmail** (recommended) or your preferred email provider
4. Follow the setup instructions to connect your Gmail account
5. **Copy the Service ID** (you'll need this later)

## Step 3: Create Email Template

1. Go to **"Email Templates"** in your dashboard
2. Click **"Create New Template"**
3. Use this template content:

**Subject:** New Contact Form Submission - {{subject}}

**Content:**

```
Hello Harisha,

You have received a new message from your portfolio contact form:

Name: {{from_name}}
Email: {{from_email}}
Subject: {{subject}}

Message:
{{message}}

---
This message was sent from your portfolio website.
```

4. **Copy the Template ID** (you'll need this later)

## Step 4: Get Public Key

1. Go to **"Account"** in your EmailJS dashboard
2. Find your **Public Key** in the API Keys section
3. **Copy the Public Key**

## Step 5: Update the Code

Replace these placeholders in your `index.html` file:

1. **Line 1792:** Replace `YOUR_PUBLIC_KEY` with your actual public key
2. **Line 1825:** Replace `YOUR_SERVICE_ID` with your service ID
3. **Line 1825:** Replace `YOUR_TEMPLATE_ID` with your template ID

Example:

```javascript
// Line 1792
emailjs.init("user_abc123def456ghi789");

// Line 1825
emailjs.send("service_xyz789", "template_abc123", templateParams);
```

## Step 6: Test the Form

1. Open your website
2. Fill out the contact form
3. Submit it
4. Check your email for the notification

## Features Included

✅ **Free tier**: 200 emails/month  
✅ **Loading states**: Button shows spinner while sending  
✅ **Success/Error notifications**: Beautiful toast notifications  
✅ **Form validation**: Built-in HTML5 validation  
✅ **Mobile responsive**: Works on all devices  
✅ **Professional styling**: Matches your portfolio design

## Alternative Free Solutions

If you prefer other options:

### 1. Formspree (50 submissions/month)

- Go to [formspree.io](https://formspree.io)
- Create account and form
- Replace form action with Formspree endpoint

### 2. Netlify Forms (if hosting on Netlify)

- Add `netlify` attribute to form
- No additional setup needed

### 3. Node.js Backend (Advanced)

- Use Nodemailer with Gmail
- Requires server setup
- More complex but fully customizable

## Troubleshooting

**Form not sending emails?**

- Check browser console for errors
- Verify all IDs are correct
- Ensure EmailJS service is active

**Emails going to spam?**

- Add SPF/DKIM records to your domain
- Use a professional email address
- Avoid spam trigger words

## Cost Breakdown

- **EmailJS Free**: 200 emails/month
- **EmailJS Paid**: $15/month for 1,000 emails
- **Formspree Free**: 50 submissions/month
- **Netlify Forms**: Free with Netlify hosting

The EmailJS free tier should be sufficient for most portfolio websites!
