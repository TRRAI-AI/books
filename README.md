
# Boekwaarde (titel + auteur)

## Backend
```
cd backend
cp .env.example .env   # vul EBAY_BEARER in
npm install
npm start              # http://localhost:3000
```

## App
```
cd boekwaarde-app
npm install
npm run start
```

- Zet in `app/App.tsx` de constante `backendUrl` naar jouw backend URL (lokaal IP of ngrok/Render).
- Open met Expo Go (QR/URL). Voor een deelbare link: `npx expo start --tunnel` of `npx expo publish`.

## GitHub: repo aanmaken & pushen

1. Maak een lege repo op GitHub, bv. `boekwaarde` (zonder README/License aanvinken).
2. In Terminal:
   ```bash
   cd /pad/naar/boekwaarde   # map waar backend/ en boekwaarde-app/ in staan
   git init
   git add .
   git commit -m "Init: boekwaarde app + backend"
   git branch -M main
   git remote add origin https://github.com/<jouw-username>/boekwaarde.git
   git push -u origin main
   ```

### Render (met render.yaml)
- Ga naar https://render.com → **New** → **Blueprint** → link naar jouw GitHub-repo.
- Render leest `render.yaml` en maakt de **Web Service** voor `backend/` aan.
- Zet in Render bij je service **Environment Variable** `EBAY_BEARER`.
- Na deploy krijg je een URL, zet die in `boekwaarde-app/app/App.tsx` bij `backendUrl`.
