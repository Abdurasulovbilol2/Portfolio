# EmailJS Setup Guide

This guide will help you set up EmailJS so that the contact form on your portfolio sends messages directly to your email inbox.

## 🚀 Quick Setup (5 minutes)

### Step 1: Create EmailJS Account
1. Go to [EmailJS.com](https://www.emailjs.com/)
2. Click **"Sign Up"** and create a free account
3. Verify your email address

### Step 2: Add Email Service
1. In your EmailJS dashboard, click **"Email Services"**
2. Click **"Add New Service"**
3. Choose **"Gmail"** (recommended) or your preferred email provider
4. Click **"Connect Account"** and authorize EmailJS to access your Gmail
5. Copy the **Service ID** (something like `service_xxxxxxx`)

### Step 3: Create Email Template
1. Go to **"Email Templates"** in your dashboard
2. Click **"Create New Template"**
3. Use this template content:

**Subject:**
```
New Contact Form Message from {{from_name}}
```

**Content:**
```
Hello Bilol,

You have received a new message through your portfolio contact form.

From: {{from_name}}
Email: {{reply_to}}

Message:
{{message}}

---
This message was sent through your QA Portfolio website.
```

4. Save the template and copy the **Template ID** (something like `template_xxxxxxx`)

### Step 4: Get Public Key
1. Go to **"Account"** → **"General"**
2. Copy your **Public Key** (something like `user_xxxxxxxxxxxxxxxx`)

### Step 5: Update Your Portfolio
1. Open `index.html` in your code editor
2. Find this line:
   ```javascript
   emailjs.init('YOUR_PUBLIC_KEY'); // Replace with your actual public key
   ```
3. Replace `YOUR_PUBLIC_KEY` with your actual public key

4. Open `script.js` and find this line:
   ```javascript
   emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams)
   ```
5. Replace:
   - `YOUR_SERVICE_ID` with your Service ID
   - `YOUR_TEMPLATE_ID` with your Template ID

### Step 6: Test Your Form
1. Open your portfolio website
2. Fill out the contact form with test information
3. Submit the form
4. Check your email inbox - you should receive the message!

## 📧 Example Configuration

After setup, your code should look like this:

**In index.html:**
```javascript
emailjs.init('user_abc123def456ghi789'); // Your actual public key
```

**In script.js:**
```javascript
emailjs.send('service_gmail123', 'template_contact456', templateParams)
```

## 🔧 Troubleshooting

### Form Not Sending
- Check browser console for error messages
- Verify all IDs are correct (Service ID, Template ID, Public Key)
- Make sure you're connected to the internet

### Not Receiving Emails
- Check your spam/junk folder
- Verify the template is set up correctly
- Make sure the email service is properly connected

### Rate Limits
- Free EmailJS accounts have limits (200 emails/month)
- For higher volumes, consider upgrading to a paid plan

## 🎯 Alternative Solutions

If you prefer not to use EmailJS, here are other options:

### 1. Formspree (Simple)
- Add `action="https://formspree.io/f/YOUR_ID"` to your form
- No JavaScript required
- Free tier: 50 submissions/month

### 2. Netlify Forms (If hosting on Netlify)
- Add `netlify` attribute to your form
- Automatic form handling
- Free tier: 100 submissions/month

### 3. Custom Backend
- Set up your own server (Node.js, Python, PHP)
- Use services like Heroku, Vercel, or Railway
- Full control but requires more setup

## 🔐 Security Notes

- Never expose private keys in client-side code
- EmailJS Public Keys are safe to use in frontend code
- Consider adding reCAPTCHA for spam protection
- Monitor your usage to avoid hitting rate limits

## 📞 Support

If you need help:
- EmailJS Documentation: https://www.emailjs.com/docs/
- EmailJS Support: support@emailjs.com
- Check browser developer console for error messages

---

Once configured, visitors to your portfolio will be able to send messages that come directly to your email inbox at **abdurasulovbiloliddin98@gmail.com**!