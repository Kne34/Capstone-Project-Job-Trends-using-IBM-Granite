# Analisis Tren Pekerjaan dengan IBM Granite

## Project Overview
Proyek ini menganalisis tren lowongan kerja global (khususnya terkait AI/Tech) untuk
mengidentifikasi **pekerjaan paling diminati**, **skill yang paling dicari**, **pola gaji**, dan
**perbedaan antar negara**. Analisis memanfaatkan Google Colab untuk EDA dan **IBM Granite 3.3 8B Instruct**
untuk menghasilkan ringkasan dan insight naratif berbasis data.

## Raw Dataset Link
[Dataset_link](https://storage.googleapis.com/kagglesdsdata/datasets/7564261/12317903/ai_job_dataset.csv?X-Goog-Algorithm=GOOG4-RSA-SHA256&X-Goog-Credential=gcp-kaggle-com%40kaggle-161607.iam.gserviceaccount.com%2F20250820%2Fauto%2Fstorage%2Fgoog4_request&X-Goog-Date=20250820T155846Z&X-Goog-Expires=259200&X-Goog-SignedHeaders=host&X-Goog-Signature=aa51fe923c34fdce2f691630a39816b4b6051edd9e2a012b12afb8c3b1d95a47e51bf7059cdd6a0c3f8566964bfbf9c8603ada12df464369522a3f0ddeb6104b79bd41d2128fdd205a7c9d3421736adc85406ada5e7ab0414b9cfb817cd740d47dca6e35e7485faa6ab4b55823beb8d1465200012dd08377cf62fd1f850520a7ea0c457a6240c1a0e1ea0ae28d9ea2b3334875e4e36974cdb74fa871138515bf23bef6e09458552801ce3c152ceca9f997f913bd894422f658a85dc402f11efa0ad4ededa5040e28c0e446e04a13b3b614270b1450535642692ca9b36dd37b9acc98e57d45225d7bc20132173de753a6acbfc654310c8338df878d45eded93a7)

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
