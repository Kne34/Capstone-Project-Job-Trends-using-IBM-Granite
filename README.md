# Analisis Tren Pekerjaan dengan IBM Granite

## Project Overview
Proyek ini menganalisis tren lowongan kerja global (khususnya terkait AI/Tech) untuk
mengidentifikasi **pekerjaan paling diminati**, **skill yang paling dicari**, **pola gaji**, dan
**perbedaan antar negara**. Analisis memanfaatkan Google Colab untuk EDA dan **IBM Granite 3.3 8B Instruct**
untuk menghasilkan ringkasan dan insight naratif berbasis data.

## Raw Dataset Link
{dataset_link}

## Analysis Process
1. **Preprocessing Data**
   - Parsing tanggal (`posting_date`, `application_deadline`), normalisasi gaji ke USD.
   - Mapping kode kategori: level pengalaman (EN/MI/SE/EX), tipe kerja (FT/PT/CT/FL), ukuran perusahaan (S/M/L).
   - Ekstraksi jumlah skill dari kolom `required_skills`.
2. **Exploratory Data Analysis (EDA)**
   - Distribusi fitur numerik: `salary_usd`, `years_experience`, `job_description_length`, `benefits_score`,
     `num_required_skills`, `remote_ratio`.
   - Distribusi fitur kategorikal: `experience_level`, `employment_type`, `company_size`, `education_required`,
     `job_title`, `company_location`, `industry`, `company_name`.
   - Agregasi per negara: top job titles, top skills, dan rata-rata gaji.
3. **Insight Generation (IBM Granite)**
   - Prompt terstruktur untuk menyusun ringkasan **per negara** (top jobs, skills, avg salary, dan insight singkat).
   - Ringkasan **global**: tren bersama, perbedaan antar negara, serta rekomendasi karier.

## Insight & Findings
- **Permintaan tinggi** pada peran: *Software/AI Engineer, Data Scientist/Analyst, ML/AI Research*.
- **Skill paling dicari**: Python, SQL, Machine Learning/Deep Learning, Cloud (AWS/GCP/Azure), MLOps.
- **Variasi gaji** signifikan antar negara; negara maju cenderung lebih tinggi untuk peran yang sama.
- **Remote ratio** cukup tinggi untuk peran software/data; membuka peluang lintas negara.
Insight ini penting untuk membantu **pelamar** memprioritaskan skill, **perusahaan** merancang strategi rekrutmen,
dan **pendidik** menyelaraskan kurikulum dengan kebutuhan industri.

## Recommendations
- Pelamar: fokus pada Python + SQL + ML/Cloud; bangun portofolio proyek dan eksplor **remote-first roles**.
- Perusahaan: perluas hiring ke model hybrid/remote untuk memperluas talent pool dan efisiensi biaya.
- Institusi pendidikan: perkuat kurikulum AI/ML, data engineering, dan komputasi awan yang aplikatif.

## AI Support Explanation
Penggunaan **IBM Granite** mempercepat pembuatan ringkasan berbasis data (country-wise dan global)
melalui *prompting* yang jelas, sehingga proses dari EDA → insight dapat diselesaikan lebih cepat dan terstruktur.
Teknik efektif yang digunakan:
- **Data-grounded prompting**: kirim ringkasan agregat (top jobs/skills, avg salary) ke model.
- **Format-constrained output**: instruksi tabel/daftar bernomor agar hasil konsisten dan mudah ditempel.
- **Iterative refinement**: memecah prompt menjadi beberapa bagian (per negara, salary insights, global trends).

---
