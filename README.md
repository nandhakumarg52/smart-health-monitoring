# ⚓ Smart Health Monitoring System (SHMS)

> A microservice-powered, AI-augmented digital healthcare solution designed for hospitals, clinics, and remote care.

---

## 🧭 Vision

To build a **modular, secure, and scalable health platform** that enables:

- Real-time patient monitoring
- Appointment & billing management
- Vitals tracking and health insights
- LLM-powered virtual assistants
- Predictive diagnostics via ML
- Computer vision from camera or imaging input

All services communicate through a central **API Gateway** and follow **microservices architecture** for easy scaling and maintainability.

---

## 📦 Core Microservices

| Service              | Responsibilities                                                                 |
|----------------------|----------------------------------------------------------------------------------|
| `auth_service`        | Auth, JWT, Roles (`admin`, `doctor`, `nurse`, `patient`)                        |
| `patient_service`     | CRUD for patient data, uploads, health notes                                    |
| `appointment_service` | Book/view/update appointments, avoid conflicts                                  |
| `vitals_service`      | Manual/device input vitals, trend alerts                                        |
| `billing_service`     | Generate invoices for consults/tests, track payments                            |
| `notification_service`| Email/SMS reminders and health alerts using Celery + RabbitMQ                   |
| `gateway`             | Central access point, routing, rate limiting, auth enforcement                  |

---

## 🧠 AI & ML Enhanced Services

| Service                 | Capabilities                                                                 |
|--------------------------|------------------------------------------------------------------------------|
| `ai_assistant_service`    | LLM-based health chat assistant, agent tool-calling, symptom checks         |
| `ml_diagnosis_service`    | Predict disease risks, recommend actions using ML models                    |
| `vision_service`          | OCR, face-based verification, anomaly detection using OpenCV                |
| `analytics_service`       | Dashboards and insights for doctors and admins via data science             |

---

## 🧙 Use Case Flow

1. Patient registers via `auth_service`
2. Profile updated through `patient_service`
3. Appointment booked using `appointment_service`
4. Nurse records vitals via `vitals_service`
5. Doctor reviews history and notes
6. `ai_assistant_service` guides pre-consult chat
7. `ml_diagnosis_service` offers risk predictions
8. `vision_service` processes uploaded scan images
9. Billing generated and tracked via `billing_service`
10. Notification sent via `notification_service`

---

## 🛡 User Roles

| Role    | Permissions                                                  |
|---------|--------------------------------------------------------------|
| Patient | Book appointments, view vitals, bills, chat with AI assistant |
| Doctor  | View patients, add notes, manage schedules                   |
| Nurse   | Record vitals, assist with patient workflows                 |
| Admin   | Full system access, manage users, billing oversight          |

---

## 🛠 Tech Stack

- **Backend**: Python (FastAPI)
- **Storage**: PostgreSQL (Local; S3 later)
- **Queue**: RabbitMQ + Celery
- **Cache**: Redis
- **ML/DS**: scikit-learn, XGBoost, pandas, MLflow
- **CV**: OpenCV, dlib, YOLO, MediaPipe
- **LLM Frameworks**: LangChain, Haystack (optional)
- **Containerization**: Docker
- **CI/CD**: GitHub Actions
- **Docs**: Swagger / OpenAPI (per service)


