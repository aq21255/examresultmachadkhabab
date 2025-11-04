# 🚀 Replit Deployment Guide - Exam Results Portal

Hageynka Replit iyo sida loo dhaqo uptime monitoring si app-ka u hawsado.

---

## 📋 Qodobada Hore

- Account Replit ah (free tier way ku filan tahay)
- GitHub repository (optional, laakiin wanaagsan)

---

## 🎯 Tallaabada 1: Sameey Project Replit cusub

1. **Tag https://replit.com**
2. **Click "Create Repl"**
3. **Dooro "Import from GitHub"** (haddii aad GitHub u haysid) ama **"Blank Repl"**
4. **Magaca Project:**
   - Magac: `exam-results-portal`
   - Language: **Node.js**
5. **Click "Create Repl"**

---

## 📁 Tallaabada 2: Upload Files

### Haddii aad isticmaasho GitHub:

1. **Tag repository-gaaga GitHub**
2. **Click "Code" → "Download ZIP"**
3. **Replit-ka, click "Files" sidebar**
4. **Drag and drop** dhammaan files-ka ZIP-ka ah

### Haddii aad upload gareyneysid:

1. **Replit Files sidebar, click "+"** (Add file/folder)
2. **Upload files-kaaga:**
   - `server.js`
   - `package.json`
   - `public/` folder (oo leh `index.html`)
   - `assets/` folder (logo, etc.)
   - `.gitignore`
   - Dhammaan files-ka kale

---

## ⚙️ Tallaabada 3: Setup Environment Variables

1. **Click "Secrets" tab** (sidebar-ka bidix)
2. **Add environment variables:**
   - Key: `PORT`
   - Value: `3000` (ama lambar aad doorbiso)
3. **Click "Add secret"**

---

## 🔧 Tallaabada 4: Setup Start Command

1. **Click `.replit` file** (ama samee haddii aan jirin)
2. **Add this content:**

```toml
run = "npm start"
entrypoint = "server.js"
```

3. **Check `package.json`** - hubi in ay leedahay:

```json
{
  "scripts": {
    "start": "node server.js"
  }
}
```

---

## 🌐 Tallaabada 5: Deploy & Run

1. **Click "Run" button** (top bar-ka)
2. **Waxay sugi doontaa** in server-ku start garo
3. **Waxaad aragtaa URL** sida:
   ```
   https://exam-results-portal.username.repl.co
   ```

---

## ⏰ Tallaabada 6: Uptime Monitoring (Maanta Muhiimsan!)

Replit free tier apps-ka waa in ay "seexaan" marka aanay shaqeyn. **Uptime monitoring** ayaa app-ka "ka kicinaya" marka walba.

### Option 1: UptimeRobot (Free - Recommended)

1. **Tag https://uptimerobot.com**
2. **Sign up** (free account)
3. **Click "Add New Monitor"**
4. **Settings:**
   - **Monitor Type:** HTTP(s)
   - **Friendly Name:** Exam Results Portal
   - **URL:** `https://exam-results-portal.username.repl.co`
   - **Monitoring Interval:** 5 minutes
5. **Click "Create Monitor"**
6. **Waxay ku ping gareyn doontaa** URL-kaaga 5 minutes kasta = app-ka ma seexanayo!

### Option 2: Cron-Job.org (Free)

1. **Tag https://cron-job.org**
2. **Sign up** (free)
3. **Click "Create cronjob"**
4. **Settings:**
   - **Title:** Keep Replit Alive
   - **Address:** `https://exam-results-portal.username.repl.co`
   - **Schedule:** Every 5 minutes
5. **Click "Create"**

### Option 3: PythonAnywhere Uptime Monitor (Free)

1. **Tag https://www.pythonanywhere.com**
2. **Sign up**
3. **Create a simple Python script:**
   ```python
   import urllib.request
   urllib.request.urlopen('https://exam-results-portal.username.repl.co')
   ```
4. **Schedule** si ay u run garto 5 minutes kasta

### Option 4: Add to Server.js (Internal Keep-Alive)

Ka dar `server.js`-kaaga dhamaadka (before `app.listen`):

```javascript
// Keep-alive endpoint for uptime monitoring
app.get('/keep-alive', (req, res) => {
    res.status(200).json({ status: 'alive', timestamp: new Date().toISOString() });
});

// Auto ping itself every 4 minutes (optional - backup)
if (process.env.KEEP_ALIVE === 'true') {
    setInterval(() => {
        fetch(`${process.env.REPL_SLUG ? `https://${process.env.REPL_SLUG}.${process.env.REPL_OWNER}.repl.co` : 'http://localhost:3000'}/keep-alive`)
            .catch(err => console.log('Keep-alive ping failed:', err));
    }, 4 * 60 * 1000); // 4 minutes
}
```

---

## 🎯 Tallaabada 7: Always-On (Paid Option)

Haddii aad rabto app-ka **always-on** (ma seexanayo):

1. **Replit, click "Settings"** (sidebar)
2. **Scroll to "Always On"**
3. **Subscribe** to Replit Core ($5/month)
4. **App-kaaga way hawsan doontaa** 24/7!

---

## 📝 Checklist

- [ ] Project Replit cusub la sameeyay
- [ ] Files-ka oo dhan la upload gareeyay
- [ ] Environment variables la dejiyay
- [ ] Server-ka la run gareeyay
- [ ] URL-ka la helay
- [ ] Uptime monitoring la dejiyay (UptimeRobot ama mid kale)
- [ ] Test gareeyay app-ka (tag URL-ka browser-ka)

---

## 🐛 Troubleshooting

### App-ka ma run gareynayo:

1. **Check console** - arag errors
2. **Check `package.json`** - hubi dependencies
3. **Run `npm install`** manually (Replit Terminal)

### App-ka seexanaya:

1. **Hubi uptime monitoring** in ay shaqeynayo
2. **Test URL** manually (tag browser-ka)
3. **Fiiro:** Replit free tier waxay "seexan karaan" 10-15 minutes inactivity kadib

### Port error:

1. **Check `.replit` file** - hubi PORT variable
2. **Replit automatic** ayaa u assign gareeyaya port
3. **Server.js-ka, hubi:**
   ```javascript
   const PORT = process.env.PORT || 3000;
   ```

---

## 🔒 Security Notes

- **Ma share gareyn** Secrets/Environment Variables
- **Hubi** .gitignore in uu database file-ka ignore garayay
- **Replit Secrets** waa ku haboon keys iyo passwords-ka

---

## 📚 Additional Resources

- **Replit Docs:** https://docs.replit.com
- **UptimeRobot:** https://uptimerobot.com
- **Cron-Job.org:** https://cron-job.org

---

## ✅ Success!

Marka dhammaan tallaabada la dhammeeyo, app-kaagu waa:
- ✅ **Online** Replit-ka
- ✅ **24/7 hawsan** (with uptime monitoring)
- ✅ **Accessible** URL-kaaga

**Good luck!** 🎉

