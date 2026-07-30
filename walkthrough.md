# Walkthrough - Production Launch & Deployment

We have successfully completed all deployment steps, database migrations, CORS integrations, and mobile compilation. Both the live website and the Android application are now fully connected to the live database and active.

---

## 🛠️ Actions Performed

### 1. Database & Schema Architecture
- Created and connected your **MongoDB Atlas** database cloud instance.
- Built schemas for:
  - **LMS Students** (`models.Student`): Handles signup, logins, and portal data.
  - **Callbacks** (`models.Callback`): Saves callback requests.
  - **Enquiries** (`models.Enquiry`): Saves contact form enquiries.
  - **Enrollments** (`models.Enrollment`): Tracks Razorpay course orders.

### 2. Live Backend Deployment (Render.com)
- Deployed the Node.js backend to Render at your new URL:
  🔗 **`https://mpulse-digi-ai-backend.onrender.com`**
- Set up secure environment variables (`MONGODB_URI`, `ADMIN_KEY`, `ALLOWED_ORIGINS`).
- Hardcoded fallback CORS support in [server.js](file:///c:/Users/user/Desktop/Mpulse%20Galaxy/MPUSLE%20DIGI-AI%20WEBSITE/backend/server.js) for your Netlify domain.

### 3. Live Frontend Deployment (Netlify)
- Updated [index.html](file:///c:/Users/user/Desktop/Mpulse%20Galaxy/MPUSLE%20DIGI-AI%20WEBSITE/frontend/index.html), [student.html](file:///c:/Users/user/Desktop/Mpulse%20Galaxy/MPUSLE%20DIGI-AI%20WEBSITE/frontend/student.html), [admin.html](file:///c:/Users/user/Desktop/Mpulse%20Galaxy/MPUSLE%20DIGI-AI%20WEBSITE/frontend/admin.html), and [class.html](file:///c:/Users/user/Desktop/Mpulse%20Galaxy/MPUSLE%20DIGI-AI%20WEBSITE/frontend/class.html) to dynamically route requests to the new Render server.
- Deployed the frontend live on Netlify:
  🔗 **`https://mpulsedigitalai.netlify.app/`**

### 4. Native Android App Build
- Updated [capacitor.config.json](file:///c:/Users/user/Desktop/Mpulse%20Galaxy/MPUSLE%20DIGI-AI%20WEBSITE/capacitor.config.json) to target the renamed `frontend` assets.
- Compiled the final production binary using Gradle:
  📱 **`C:\Users\user\Desktop\mpulse_production.apk`**

---

## 🧪 Verification & Results

We tested all endpoints and verified successful saves in the live MongoDB database:

| Action | API Endpoint | Status | Saved in MongoDB? |
| :--- | :--- | :---: | :---: |
| **Contact Enquiry** | `/api/enquiry` | `200 OK` | Yes ✅ |
| **Callback Request** | `/api/callback` | `200 OK` | Yes ✅ |
| **LMS Signup** | `/api/auth/signup` | `200 OK` | Yes ✅ |
| **Dashboard Query** | `/api/admin/lms-students` | `200 OK` | Yes ✅ |

### Live DB Proof (Last Student Registered via Live Website):
```json
{
  "_id": "6a4645dc268269f387b3b746",
  "name": "sandy",
  "email": "haisandy@gmail.com",
  "phone": "6302805203",
  "createdAt": "2026-07-02T11:05:00.144Z"
}
```

---

## 📈 Next Steps

1. **Verify on your Phone**: Install the updated `mpulse_production.apk` saved on your Desktop to test the mobile app!
2. **Access Admin Panel**: Go to [https://mpulsedigitalai.netlify.app/admin.html](https://mpulsedigitalai.netlify.app/admin.html) using key `mpulseadmin` to manage entries!
