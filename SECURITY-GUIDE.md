# 🔒 Admin Security Setup Guide

## ⚙️ Configure Your Access

### Step 1: Set Your Authorized Emails & Passwords

Open `admin-prices.html` and find this section (around line 232):

```javascript
const AUTHORIZED_USERS = [
  {
    email: "admin@martdokpetroleum.com",
    password: "MartDok2025!", // CHANGE THIS PASSWORD!
  },
  {
    email: "manager@martdokpetroleum.com",
    password: "Manager2025!", // CHANGE THIS PASSWORD!
  },
  // Add more authorized users here
];
```

**📝 To Add Yourself:**

1. Replace the email with YOUR email address
2. Change the password to a STRONG password
3. Add more users if needed

**Example:**

```javascript
const AUTHORIZED_USERS = [
  {
    email: "yourname@gmail.com",
    password: "MyStr0ng!Pass2025",
  },
  {
    email: "partner@company.com",
    password: "Another$ecurePass",
  },
];
```

---

### Step 2: Optional - IP Whitelist (Extra Security)

If you want to restrict access to specific IP addresses only:

```javascript
const WHITELISTED_IPS = [
  "102.89.45.123", // Your office IP
  "197.210.55.87", // Your home IP
];
```

**🌐 How to Find Your IP Address:**

- Visit: https://whatismyipaddress.com/
- Copy the "IPv4" address shown
- Paste it into the WHITELISTED_IPS array

**⚠️ Important:**

- Leave empty `[]` if you want email/password only (recommended)
- IP addresses can change (especially on mobile networks)
- If you get locked out, just empty this array

---

## 🔐 Security Features

✅ **Email & Password Protection**

- Only registered emails can login
- Wrong credentials = Access denied

✅ **IP Whitelist (Optional)**

- Restrict access to specific IP addresses
- Double layer of security

✅ **Session Management**

- Auto-logout when browser closes
- "Logout" button available

✅ **Real-time IP Display**

- Shows your current IP address on login screen
- Helps you know which IP to whitelist

---

## 🎯 How to Login

1. Open `admin-prices.html` in browser
2. Enter your registered email
3. Enter your password
4. Click "Login to Admin Panel"
5. ✓ Access granted!

---

## 🆘 Troubleshooting

### "Access Denied" Error

**Problem:** Invalid email or password
**Solution:** Check your email/password in AUTHORIZED_USERS array

**Problem:** IP address not authorized
**Solution:**

- Add your IP to WHITELISTED_IPS array
- OR remove all IPs from whitelist (set to `[]`)

### Forgot Password

1. Open `admin-prices.html` in code editor
2. Find AUTHORIZED_USERS section
3. Change password to new one
4. Save file
5. Try logging in again

### Lost Access Completely

1. Open `admin-prices.html`
2. Delete entire WHITELISTED_IPS array (make it empty: `[]`)
3. Reset password in AUTHORIZED_USERS
4. Save and reload

---

## 🛡️ Security Best Practices

1. **Use Strong Passwords**

   - Mix uppercase, lowercase, numbers, symbols
   - At least 12 characters
   - Don't use "password123" or company name

2. **Don't Share Credentials**

   - Each admin should have own email/password
   - Don't send passwords via email/WhatsApp

3. **Change Passwords Regularly**

   - Update every 3-6 months
   - Change immediately if compromised

4. **Keep File Secure**

   - Don't upload `admin-prices.html` to public website
   - Keep it on your local computer
   - Or put in password-protected folder on server

5. **Logout When Done**
   - Always click "Logout" button
   - Especially on shared computers

---

## 📱 Multiple Admins Setup

Want to give access to multiple people? Just add them:

```javascript
const AUTHORIZED_USERS = [
  {
    email: "ceo@martdokpetroleum.com",
    password: "CEO$ecurePass2025",
  },
  {
    email: "accountant@martdokpetroleum.com",
    password: "Acc0unt!ng2025",
  },
  {
    email: "manager@martdokpetroleum.com",
    password: "Man@ger2025Pass",
  },
];
```

Each person gets their own:

- Email address
- Password
- Can login independently

---

## 🔄 How to Remove Access

To revoke someone's access:

1. Open `admin-prices.html`
2. Find their entry in AUTHORIZED_USERS
3. Delete the entire block:

```javascript
{
  email: 'person@email.com',
  password: 'TheirPassword'
},  // ← Delete this whole section including comma
```

4. Save file
5. They can't login anymore

---

## 📊 What Happens After Login

Once logged in, you can:

- ✅ Update all diesel prices
- ✅ Generate code snippets
- ✅ See current prices
- ✅ Copy code to clipboard
- ✅ Logout anytime

Your session remains active until:

- You click "Logout"
- You close the browser
- Session expires (for security)

---

## 🚨 Emergency: I'm Locked Out!

If you can't login:

1. **Open admin-prices.html in code editor**
2. **Find line ~245** (AUTHORIZED_USERS section)
3. **Change to this temporary access:**

```javascript
const AUTHORIZED_USERS = [
  {
    email: "emergency@access.com",
    password: "emergency123",
  },
];

const WHITELISTED_IPS = []; // Make sure this is empty!
```

4. **Save file**
5. **Login with:** emergency@access.com / emergency123
6. **Update prices**
7. **Then change back to your secure credentials!**

---

## 💡 Pro Tips

- Keep a backup copy of your AUTHORIZED_USERS config
- Write down your password in a safe place (not on computer)
- Test login after making changes
- Use Chrome/Firefox for best experience
- Check IP address changes if using IP whitelist

---

**Questions?** Check the code comments in `admin-prices.html` - everything is well-documented!

Stay secure! 🔒
