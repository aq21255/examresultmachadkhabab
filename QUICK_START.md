# ⚡ Quick Start - Online Deploy (5 Daqiiqo!)

Hageynka ugu **fudud** ee online deployment-ka. **5 daqiiqo oo kaliya!**

---

## 🚀 Option 1: Railway.app (Ugu Fudud ⭐⭐⭐)

### Tallaabada (3 clicks oo kaliya):

1. **GitHub-ka upload code:**
   ```bash
   git init
   git add .
   git commit -m "First commit"
   ```
   - Tag https://github.com
   - Click "New repository"
   - Name: `exam-results`
   - Click "Create"
   - Run these commands:
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/exam-results.git
   git branch -M main
   git push -u origin main
   ```

2. **Railway-ka deploy:**
   - Tag https://railway.app
   - Click "Start a New Project"
   - Click "Deploy from GitHub repo"
   - Dooro repository-gaaga
   - **Done!** 🎉

3. **Hel URL-kaaga:**
   - Railway dashboard → Settings → Generate Domain
   - Copy URL-ka (sida: `https://exam-results.up.railway.app`)

**✅ Done! App-kaagu waa online!**

---

## 🚀 Option 2: Render.com (100% FREE)

### Tallaabada:

1. **GitHub upload** (same as above)

2. **Render deploy:**
   - Tag https://render.com
   - Sign up with GitHub
   - Click "New +" → "Web Service"
   - Connect repository-gaaga
   - Settings:
     - Build Command: `npm install`
     - Start Command: `npm start`
     - Plan: **Free**
   - **IMPORTANT:** Scroll down, check **"Enable Always-On"** ✅
   - Click "Create Web Service"

3. **Hel URL-kaaga:**
   - Render automatic ayaa bixinaya (sida: `https://exam-results.onrender.com`)

**✅ Done!**

---

## 📋 Pre-Deploy Checklist:

- [ ] `package.json` waa jiraa
- [ ] `server.js` waa jiraa
- [ ] `public/index.html` waa jiraa
- [ ] Code-ka oo dhan waa ka jiraa folder-ka

---

## ⚠️ Important Notes:

### Server.js PORT:
Hubi in `server.js`-kaaga ay leedahay:
```javascript
const PORT = process.env.PORT || 5000;
```

### Always-On (Render):
- **MUST enable "Always-On"** si app-ka u seexanayo
- Settings → Advanced → Enable Always-On ✅

### Railway:
- **Automatic always-on** - ma baahno enable!

---

## 🆘 Haddii Qalad Jiro:

### "Build failed":
- Check logs (Dashboard → Logs)
- Hubi `package.json` in uu sax yahay
- Hubi dependencies-ka in ay install garayeen

### App-ka ma shaqeeyo:
- Hubi URL-ka in uu sax yahay
- Test `/keep-alive` endpoint (si uu u shaqeeyo)
- Check logs for errors

---

## ✅ Success!

Marka tallaabada la dhammeeyo:
- ✅ App-kaagu waa online
- ✅ URL-kaaga waa ku filan
- ✅ Ma seexanayo (always-on)

**Enjoy! 🎉**

---

## 💡 Quick Tips:

1. **Railway** = Ugu fudud (3 clicks)
2. **Render** = 100% free always-on
3. Both platforms = Automatic SSL, Auto-deploy

**Choose one and go! 🚀**

