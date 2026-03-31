# 🤖 RobotPlus

> Sanoat robotlarining buzilishini bashorat qilish va oldini olish tizimi

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?logo=python&logoColor=white)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.110+-009688?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![React](https://img.shields.io/badge/React-18+-61DAFB?logo=react&logoColor=black)](https://react.dev)

---

## 📌 Loyiha haqida

**RobotPlus** — sanoat korxonalarida ishlatilayotgan robotlarning texnik holati real vaqtda kuzatib boriladigan, nosozliklar oldindan bashorat qilinadigan va profilaktik ta'mirlash rejalashtirib beriladigan dasturiy platforma.

**Asosiy muammolar hal qilinadi:**
- Kutilmagan robot buzilishlari sabab ishlab chiqarish to'xtab qolishi
- Texnik xizmat ko'rsatish jadvalini qo'lda tuzish qiyinchiliklari
- Sensor ma'lumotlarini real vaqtda tahlil qila olmaslik

---

## 🗂 Loyiha tuzilishi (Monorepo)

```
RobotPlus/
├── backend/          ← Python / FastAPI (Backend Developer ishlaydi)
│   ├── app/
│   │   ├── api/      # Route'lar va endpoint'lar
│   │   ├── core/     # Konfiguratsiya, sozlamalar
│   │   ├── models/   # Ma'lumotlar modellari
│   │   ├── services/ # Biznes logika
│   │   └── ml/       # Bashorat qilish modellari
│   ├── tests/
│   ├── requirements.txt
│   └── main.py
│
├── frontend/         ← React (Frontend Developer ishlaydi)
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── hooks/
│   │   ├── services/ # API bilan bog'lanish
│   │   └── store/    # State management
│   ├── public/
│   └── package.json
│
├── .gitignore
└── README.md
```

---

## 👥 Komanda va rollar

### 🎨 Frontend Developer

**Ishlaydigan papkasi:** `frontend/`

**Mas'uliyat:**
- UI komponentlar yaratish va qo'llab-quvvatlash
- Backend API bilan integratsiya (`/frontend/src/services/`)
- Real vaqt dashboard (sensorlar, grafik, ogohlantirishlar)
- Responsive dizayn va UX

**Texnologiyalar:**
- React 19+
- React Router
- Axios / TanStack Query
- Recharts (grafik va vizualizatsiya)

**Ishni boshlash:**
```bash
cd frontend
bun install
bun dev
```

---

### ⚙️ Backend Developer

**Ishlaydigan papkasi:** `backend/`

**Mas'uliyat:**
- REST API yaratish va qo'llab-quvvatlash
- Ma'lumotlar bazasi modellari va migratsiyalar
- ML modellarini API orqali chiqarish
- Autentifikatsiya va avtorizatsiya
- WebSocket orqali real vaqt ma'lumot uzatish

**Texnologiyalar:**
- Python 3.14+
- FastAPI
- SQLAlchemy / Alembic
- PostgreSQL
- scikit-learn / PyTorch (ML uchun)

**Ishni boshlash:**
```bash
cd backend
poetry install
poetry run uvicorn main:app --reload
```

---

## 🚀 Loyihani ishga tushirish

### Talablar

| Asbob | Versiya |
|-------|---------|
| Node.js | 22+ |
| Python | 3.14+ |
| PostgreSQL | 17+ |
| Git | 2.40+ |

### 1. Repozitoriyni klonlash

```bash
git clone https://github.com/thisisal1yev/RobotPlus.git
cd RobotPlus
```

### 2. Backend sozlash

```cd backend
poetry install

# .env faylini yarating
cp .env.example .env
# .env ichidagi o'zgaruvchilarni to'ldiring

# Ma'lumotlar bazasini migratsiya qilish
poetry run alembic upgrade head

# Serverni ishga tushirish
poetry run uvicorn main:app --reload --port 8000
```

### 3. Frontend sozlash

```bash
cd frontend
bun install

# .env faylini yarating
cp .env.example .env
# REACT_APP_API_URL=http://localhost:8000

# Dev serverni ishga tushirish
bun dev
```

### 4. Tekshirish

- Frontend: [http://localhost:5173](http://localhost:5173)
- Backend API: [http://localhost:8000](http://localhost:8000)
- API doc: [http://localhost:8000/docs](http://localhost:8000/docs)

---

## 🌿 Git workflow

```
main          ← faqat production-ready kod
  └── dev     ← asosiy ishchi branch
        ├── feature/frontend-dashboard
        ├── feature/backend-auth
        └── fix/sensor-data-parsing
```

**Branch nomlash qoidasi:**
```
feature/<qisqa-tavsif>   # yangi funksiya
fix/<qisqa-tavsif>       # xatolikni tuzatish
refactor/<qisqa-tavsif>  # kodni qayta yozish
```

**PR ochishdan oldin:**
- [ ] Kod o'z branchingizda yozilgan (`main`/`dev`ga to'g'ridan-to'g'ri push yo'q)
- [ ] Testlar yozilgan va o'tgan
- [ ] `dev` branch bilan merge conflict yo'q

---

## 📡 API hujjatlari

Backend ishga tushirilgandan so'ng:

- **Swagger UI:** `http://localhost:8000/docs`
