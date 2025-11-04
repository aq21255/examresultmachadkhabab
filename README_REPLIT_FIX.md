# 🔧 Fix Replit - Run Node.js Instead of Python

Replit-ku wuxuu u maleynayaa Python project maxaa yeelay `app.py` iyo `requirements.txt` ay ku jiraan. Halkan sida loo fix garo:

---

## ✅ Solution: Configure Replit for Node.js

### **Step 1: Replit Configuration**

1. **Replit-ka**, click **"Tools"** (left sidebar - gear icon)
2. **Click ".replit" file** (ama create haddii aan jirin)
3. **Hubi in ay leedahay:**
   ```
   run = "npm start"
   entrypoint = "server.js"
   language = "nodejs"
   ```

4. **Haddii Python ku jiro**, **change** garay → `nodejs`

---

### **Step 2: Delete or Move Python Files (Optional)**

**Option A: Delete Python Files** (haddii aadan Python app u baahneyn):
1. **Replit Files sidebar**, **right-click** `app.py`
2. **Click "Delete"**
3. **Same with** `requirements.txt` (haddii aan loo baahnayn)

**Option B: Move to Archive Folder** (haddii aad Python files-ka u rabto):
1. **Create folder:** `old_python_files/`
2. **Move** `app.py` → `old_python_files/`
3. **Move** `requirements.txt` → `old_python_files/`

---

### **Step 3: Stop and Restart**

1. **Click "Stop" button** (top - red button)
2. **Click "Run" button** again (green button)
3. **Replit** waa in uu detect garayaa Node.js project

---

### **Step 4: Verify It's Running Node.js**

1. **Terminal** (bottom panel), waxaad aragtaa:
   ```
   npm install
   ...
   Server running on http://localhost:5000
   ```

2. **Haddii Python ku muujinayo**, `.replit` file-ka hubi again

---

## 🎯 Quick Fix (All at Once):

1. **Create/Update `.replit` file:**
   ```toml
   run = "npm start"
   entrypoint = "server.js"
   language = "nodejs"
   ```

2. **Delete** `app.py` (haddii aan loo baahnayn)

3. **Stop** → **Run** again

4. **Done!** ✅

---

## 📝 Notes:

- **Design-ka saxda ah** waa ku jira `public/index.html` (green/Islamic theme)
- **Design-ka qaldan** waa ku jira root `index.html` (purple - old version)
- **Server.js** waa in uu serve garayaa `public/index.html` ✅

---

**Good luck! 🚀**

