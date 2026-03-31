# ⚙️ RobotPlus Backend

> FastAPI asosidagi REST API va real vaqt ma'lumotlar qatlami

[![Python](https://img.shields.io/badge/Python-3.14+-3776AB?logo=python&logoColor=white)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.110+-009688?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)

---

## 📌 Backend haqida

`backend/` qismi RobotPlus platformasining server tomonini tashkil qiladi:
- robotlardan keladigan sensor ma'lumotlarini qabul qiladi
- nosozliklarni bashorat qilish uchun ML servislarini ishga tushiradi
- frontend uchun REST API va hujjatlashtirilgan endpointlar beradi
- autentifikatsiya, avtorizatsiya va audit logikalarini boshqaradi

---

## 🗂 Tuzilma

```text
backend/
├── app/
│   ├── api/         # Route va endpointlar
│   ├── core/        # Konfiguratsiya va umumiy sozlamalar
│   ├── models/      # ORM / domen modellari
│   ├── services/    # Biznes logika
│   └── ml/          # ML inferens va model util'lar
├── tests/           # Unit/integration testlar
├── requirements.txt # Muqobil dependency ro'yxati
└── main.py          # Uvicorn kirish nuqtasi
```

---

## 🧰 Texnologiyalar

- Python 3.14+
- FastAPI
- SQLAlchemy / Alembic
- PostgreSQL
- scikit-learn / PyTorch (ML)

---

## 🚀 Ishga tushirish

### 1) Muhitni tayyorlash

```bash
cd backend
poetry install
```

### 2) Konfiguratsiya

```bash
cp .env.example .env
```

`.env` faylida kamida quyidagilarni to'ldiring:
- `DATABASE_URL`
- `SECRET_KEY`
- `ACCESS_TOKEN_EXPIRE_MINUTES`
- `CORS_ORIGINS`

### 3) Migratsiya

```bash
poetry run alembic upgrade head
```

### 4) Servisni ishga tushirish

```bash
poetry run uvicorn main:app --reload --port 8000
```

---

## 🧪 Testlar va sifat nazorati

```bash
# testlar
poetry run pytest

# kod formatlash/lint (agar sozlangan bo'lsa)
poetry run ruff check .
poetry run ruff format .
```

---

## 📡 Foydali manzillar

- API: [http://localhost:8000](http://localhost:8000)
- Swagger: [http://localhost:8000/docs](http://localhost:8000/docs)

---

## 🤝 Integratsiya (Frontend bilan)

Frontend servis qatlamida backend URL odatda quyidagiga yo'naltiriladi:

```env
REACT_APP_API_URL=http://localhost:8000
```

Endpointlarda CORS sozlamasi frontend domeniga mos bo'lishi kerak.

