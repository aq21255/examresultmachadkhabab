# 🚀 Fly.io Deployment Guide (FREE - Ma Sleep Garayno)

Fly.io waa FREE oo **ma sleep garayno** - online 24/7!

---

## 📋 Step-by-Step Guide

### Step 1: Fly.io Account-ka Samee

1. **Browser-ka ku tag:**
   ```
   https://fly.io/app/sign-up
   ```

2. **Sign up:**
   - Gali email-kaaga ama GitHub-ka use garee
   - Password samee
   - Click "Sign Up"

3. **Email verify garee:**
   - Check email-kaaga
   - Click verification link-ka

---

### Step 2: Fly CLI Install Garee (Windows)

1. **PowerShell ku fur:**
   - Press `Windows + X`
   - Choose "Windows PowerShell (Admin)"

2. **Install command-ka run garee:**
   ```powershell
   powershell -Command "iwr https://fly.io/install.ps1 -useb | iex"
   ```

3. **Hubi in uu install garay:**
   ```powershell
   fly version
   ```
   Haddii version-ka tusayo, waa sax! ✅

---

### Step 3: Fly.io Login Garee

1. **Terminal/PowerShell ku fur**

2. **Login command-ka run garee:**
   ```powershell
   fly auth login
   ```
   
3. **Browser-ka ayaa kusoo furmaya:**
   - Click "Authorize" oo ku login garee
   - Automatic ku return garaynayaa terminal-ka

---

### Step 4: Project Directory-ka Gal

1. **Terminal-ka project directory-kaaga gal:**
   ```powershell
   cd "C:\Users\Refubz\OneDrive\Desktop\exam results khabab"
   ```

2. **Hubi in files-ka ay jiraan:**
   ```powershell
   dir
   ```
   Waa inaad arkeysid: `server.js`, `package.json`, `public/`

---

### Step 5: Fly.io App-ka Launch Garee

1. **Launch command-ka run garee:**
   ```powershell
   fly launch
   ```

2. **Questions-ka ka jawaab:**
   
   **Question 1: App name?**
   ```
   Enter a name for your app: khabbab-exam-results
   ```
   (ama mid kale - must be unique globally)
   
   **Question 2: Region?**
   ```
   Select region: 
   > 1: ams (Amsterdam)
     2: ord (Chicago)
     3: dfw (Dallas)
     4: fra (Frankfurt)
     5: gru (São Paulo)
     6: hkg (Hong Kong)
     7: iad (Ashburn)
     8: lax (Los Angeles)
     9: lhr (London)
     10: nrt (Tokyo)
     11: sea (Seattle)
     12: sin (Singapore)
     13: syd (Sydney)
   ```
   Choose one close to you (e.g., `lhr` for London, `iad` for US East)
   
   **Question 3: Postgres?**
   ```
   Would you like to set up a Postgres database now? (y/N): N
   ```
   Press `N` (ma u baahanno - SQLite baan isticmaaleynaa)
   
   **Question 4: Redis?**
   ```
   Would you like to set up a Redis database now? (y/N): N
   ```
   Press `N`
   
   **Question 5: Deploy now?**
   ```
   Would you like to deploy now? (y/N): y
   ```
   Press `y` to deploy!

3. **Fly wuxuu automatic:**
   - Create `fly.toml` file (configuration)
   - Deploy your app
   - Give you a URL

---

### Step 6: fly.toml Configuration-ka Hagaaji

Haddii deployment-ka ay qalad kusoo baxo, `fly.toml` file-ka hagaaji:

1. **fly.toml file-ka fur:**
   - Project-kaaga directory-ka gudaha `fly.toml` file-ka fur

2. **Hagaaji content-ka:**
   ```toml
   app = "khabbab-exam-results"
   primary_region = "lhr"  # or whatever region you chose

   [build]
     builder = "paketobuildpacks/builder:base"

   [http_service]
     internal_port = 5000
     force_https = true
     auto_stop_machines = false
     auto_start_machines = true
     min_machines_running = 1
     processes = ["app"]

     [[http_service.checks]]
       grace_period = "10s"
       interval = "30s"
       method = "GET"
       timeout = "5s"
       path = "/"

   [[vm]]
     cpu_kind = "shared"
     cpus = 1
     memory_mb = 256
   ```

3. **Save garee file-ka**

---

### Step 7: Deploy Garee

1. **Deploy command-ka run garee:**
   ```powershell
   fly deploy
   ```

2. **Wait garee deployment-ka:**
   - Takes 2-5 minutes
   - You'll see build logs

3. **Haddii successful:**
   ```
   ✓ Deployment successful!
   App URL: https://khabbab-exam-results.fly.dev
   ```

---

### Step 8: App-ka Test Garee

1. **Browser-ka URL-ka ku tag:**
   ```
   https://YOUR_APP_NAME.fly.dev
   ```

2. **Test garee:**
   - Homepage-ka arag
   - Search by exam number test garee
   - Admin login test garee

---

## 🔧 Troubleshooting

### Problem 1: Port Configuration Wrong

**Solution:** Hagaaji `fly.toml`:
```toml
[http_service]
  internal_port = 5000  # Make sure this matches your server PORT
```

### Problem 2: App Won't Start

**Solution:** Check logs:
```powershell
fly logs
```

### Problem 3: Need to Update App

**Solution:** Simply redeploy:
```powershell
fly deploy
```

### Problem 4: App Name Already Taken

**Solution:** Choose different name:
```powershell
fly launch --name khabbab-exam-results-unique
```

---

## 📊 Useful Commands

```powershell
# View app status
fly status

# View logs
fly logs

# Open app in browser
fly open

# SSH into app
fly ssh console

# Restart app
fly apps restart

# Scale app (if needed)
fly scale count 1

# View app info
fly info
```

---

## ✅ Post-Deployment Checklist

1. ✅ Test homepage
2. ✅ Test student search
3. ✅ Test admin login (admin/admin123)
4. ✅ Change default admin password
5. ✅ Test add/edit/delete students
6. ✅ Test ID card printing
7. ✅ Test QR code generation

---

## 🎉 Done!

Your app is now:
- ✅ Online 24/7 (ma sleep garayno!)
- ✅ FREE tier
- ✅ Accessible at: `https://YOUR_APP_NAME.fly.dev`
- ✅ Automatic HTTPS/SSL

**To update your app in future:**
```powershell
fly deploy
```

That's it! 🚀

