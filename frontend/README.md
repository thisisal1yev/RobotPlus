# 🎨 RobotPlus Frontend

> React asosidagi monitoring dashboard va operator interfeysi

[![React](https://img.shields.io/badge/React-19+-61DAFB?logo=react&logoColor=black)](https://react.dev)
[![Bun](https://img.shields.io/badge/Bun-1.0+-000000?logo=bun&logoColor=white)](https://bun.sh)

---

## 📌 Frontend haqida

`frontend/` qismi RobotPlus platformasining foydalanuvchi interfeysini ta'minlaydi:
- sensor holatini real vaqtga yaqin monitoring qilish
- ogohlantirishlar va nosozlik ehtimolini vizual ko'rsatish
- backend API bilan integratsiya qilib boshqaruv oynalarini taqdim etish
- turli ekran o'lchamlari uchun responsive UX berish

---

## 🗂 Tuzilma

```text
frontend/
├── src/
│   ├── components/  # Qayta ishlatiladigan UI komponentlar
│   ├── pages/       # Asosiy sahifalar
│   ├── hooks/       # Custom React hooks
│   ├── services/    # API client va so'rovlar
│   └── store/       # State management
├── public/          # Statik fayllar
└── package.json
```

---

## 🧰 Texnologiyalar

- React 19+
- React Router
- Axios / TanStack Query
- Recharts
- Bun

---

## 🚀 Ishga tushirish

### 1) Dependency o'rnatish

```bash
cd frontend
bun install
```

### 2) Konfiguratsiya

```bash
cp .env.example .env
```

`.env` ichida backend URL ni kiriting:

```env
REACT_APP_API_URL=http://localhost:8000
```

### 3) Development server

```bash
bun dev
```

---

## 🧪 Tekshirish va build

```bash
# lint (agar sozlangan bo'lsa)
bun run lint

# production build
bun run build

# build preview (agar mavjud bo'lsa)
bun run preview
```

---

## 🔗 Foydali manzillar

- Frontend (dev): [http://localhost:5173](http://localhost:5173)
- Backend API: [http://localhost:8000](http://localhost:8000)
- API hujjati: [http://localhost:8000/docs](http://localhost:8000/docs)

---

## 🤝 Backend bilan ishlash

- API chaqiriqlari `src/services/` ichida markazlashtiriladi
- Har bir yangi endpoint uchun typed service funksiyalar yozish tavsiya etiladi
- Xatoliklar UI'da bir xil formatda ko'rsatilishi uchun umumiy error handler ishlating

