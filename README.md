# Rotam-Yazilim
This is a project for 5th term of UNIDES projects and also Software Project Managment
import google.ds_python_interpreter as ds

readme_content = """# 🚀 Rotam Ünides - Yazılım Uzmanlık Alanı Analiz Platformu

**Rotam Ünides**, öğrencilerin bilişim sektöründeki yatkınlıklarını analiz ederek onlara en uygun yazılım uzmanlık alanını (Frontend, Backend, Mobil, Siber Güvenlik, Yapay Zeka) belirleyen full-stack bir web uygulamasıdır. 

Proje, kurumsal standartlarda **Katmanlı Mimari (Layered Architecture)**, **DTO (Data Transfer Object)** paternleri ve **JWT (JSON Web Token)** tabanlı güvenlik mekanizmaları üzerine inşa edilmiştir.

---

## 🛠️ Teknoloji Yığını (Tech Stack)

### Backend
* **Dil:** Java 21
* **Framework:** Spring Boot 4.0.3
* **Güvenlik:** Spring Security & JWT (Stateless)
* **Veri Erişimi:** Spring Data JPA / Hibernate
* **Veritabanı:** MySQL
* **Araçlar:** Spring Tool Suite (STS), Maven, Lombok

### Frontend
* **Kütüphane:** React 18
* **Build Tool:** Vite
* **HTTP Client:** Axios
* **Router:** React Router DOM
* **Araçlar:** VS Code

---

## 🏗️ Mimari Yapı

Proje, "Separation of Concerns" (Sorumlulukların Ayrılması) prensibine uygun olarak katmanlara ayrılmıştır:

1.  **Controller Layer:** REST API endpoint'lerinin tanımlandığı ve isteklerin karşılandığı katman.
2.  **Service Layer:** İş mantığının (Business Logic) yürütüldüğü katman.
3.  **Repository Layer:** Veritabanı CRUD işlemlerinin yönetildiği katman (Spring Data JPA).
4.  **Entity Layer:** Veritabanı tablolarına karşılık gelen JPA modelleri.
5.  **DTO (Data Transfer Object):** Entity'lerin API üzerinden doğrudan sunulmasını engelleyen, veri güvenliğini ve performansını artıran taşıma nesneleri.

---

## ⚙️ Kurulum ve Çalıştırma

### 1. Veritabanı Hazırlığı
* PostgreSQL üzerinde `postgres` (veya tercih ettiğiniz isimde) bir veritabanı oluşturun.
* DBeaver üzerinden bağlantınızı test edin.

### 2. Backend Kurulumu (Spring Boot)
1.  `src/main/resources/application.properties` dosyasını açın ve veritabanı bilgilerinizi güncelleyin:
    ```properties
    spring.datasource.url=jdbc:postgresql://localhost:5432/postgres
    spring.datasource.username=postgres
    spring.datasource.password=1
    jwt.secret=cok_gizli_sifre
    ```
2.  STS (Spring Tool Suite) üzerinden projeyi **Run as Spring Boot App** olarak başlatın.
3.  Uygulama varsayılan olarak `http://localhost:8080` portunda çalışacaktır.

### 3. Frontend Kurulumu (React + Vite)
1.  Terminali açın ve frontend klasörüne gidin.
2.  Bağımlılıkları yükleyin:
    ```bash
    npm install
    ```
3.  Ana dizinde `.env` dosyası oluşturun ve API adresini tanımlayın:
    ```env
    VITE_API_URL=http://localhost:8080
    ```
4.  Uygulamayı başlatın:
    ```bash
    npm run dev
    ```
5.  Tarayıcıda localde çalıştırmak için`http://localhost:5173` , canlı halini çalıştırmak için
‘https://www.rotamyazilim.xyz/’ adresine giderek testi başlatabilirsiniz.

---

## 🔐 Güvenlik ve Yetkilendirme

Uygulama iki farklı admin rolü barındırır:
* **Super Admin:** Tüm okulları görebilir, soruları düzenleyebilir ve tüm raporları indirebilir.
* **School Admin:** Sadece kendi okuluna ait öğrenci listesini, istatistiklerini görebilir ve Excel raporu alabilir.

Tüm admin işlemleri **JWT Filter** üzerinden geçerek doğrulanır. `OPTIONS` preflight istekleri CORS politikasına uygun olarak yönetilir.

---

## 👥 Ekip Üyeleri
* Hüseyin Özaydın
* Muhammed Bayram
* Tarık Karaismailoğlu


---

## 📜 Lisans
Bu proje eğitim amaçlı geliştirilmiştir. Tüm hakları saklıdır.
"""

with open("README.md", "w", encoding="utf-8") as f:
    f.write(readme_content)

print("README.md dosyası başarıyla oluşturuldu.")
