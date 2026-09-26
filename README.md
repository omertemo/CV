# 📄 LaTeX CV Template

XeLaTeX tabanlı, modüler, çift dilli (EN/TR) özgeçmiş şablonu. Fork'layıp kendi bilgilerinizi girerek hemen kullanmaya başlayabilirsiniz.

## 📸 Önizleme

| İngilizce | Türkçe |
|-----------|--------|
| [english_cv.pdf](english_cv.pdf) | [turkish_cv.pdf](turkish_cv.pdf) |

---

## 🚀 Hızlı Başlangıç

### 1. Repo'yu Klonlayın

```bash
git clone https://github.com/<kullanici-adiniz>/CV.git
cd CV
```

### 2. Kişisel Bilgilerinizi Güncelleyin

Ana dosyalarda (`english_cv.tex` ve/veya `turkish_cv.tex`) **PERSONAL INFORMATION** bölümünü düzenleyin:

```latex
\name{Ad}{Soyad}
\position{Unvanınız{\enskip\cdotp\enskip}Alt Unvan}
\address{ŞEHİR}
\mobile{+90 5XX XXX XX XX}
\email{email@example.com}
\homepage{website.com}
\github{github.com/kullanici}
\linkedin{linkedin.com/in/kullanici}
```

### 3. CV İçeriklerini Düzenleyin

Her bölüm ayrı bir `.tex` dosyasında tutulur. Düzenlemek istediğiniz dosyayı açıp içeriği değiştirin:

| Bölüm | İngilizce | Türkçe |
|-------|-----------|--------|
| Eğitim | `cv/education.tex` | `cv_tr/education.tex` |
| Deneyim | `cv/experience.tex` | `cv_tr/experience.tex` |
| Projeler | `cv/projects.tex` | `cv_tr/projects.tex` |
| Yetenekler | `cv/skills.tex` | `cv_tr/skills.tex` |
| Sertifikalar | `cv/ceritificates.tex` | `cv_tr/certificates.tex` |
| Diller | `cv/languages.tex` | `cv_tr/languages.tex` |

### 4. PDF Oluşturun

```bash
# İngilizce CV
xelatex english_cv.tex

# Türkçe CV
xelatex turkish_cv.tex
```

> [!IMPORTANT]
> Bu şablon **XeLaTeX** gerektirir. Standart `pdflatex` ile derlenmez.

---

## 📁 Proje Yapısı

```
CV/
├── english_cv.tex       # İngilizce CV ana dosyası
├── turkish_cv.tex       # Türkçe CV ana dosyası
├── russell.cls          # LaTeX class dosyası (şablon stili)
├── profile.png          # Profil fotoğrafı (isteğe bağlı)
├── cv/                  # İngilizce içerik dosyaları
│   ├── education.tex
│   ├── experience.tex
│   ├── projects.tex
│   ├── skills.tex
│   ├── ceritificates.tex
│   ├── languages.tex
│   ├── summary.tex
│   ├── achievements.tex
│   └── interests.tex
├── cv_tr/               # Türkçe içerik dosyaları
│   ├── education.tex
│   ├── experience.tex
│   ├── projects.tex
│   ├── skills.tex
│   ├── certificates.tex
│   └── languages.tex
└── fonts/               # Roboto & FontAwesome fontları
```

---

## 🛠 Gereksinimler

- **TeX Live** (2022+) veya **MacTeX**
- XeLaTeX derleyicisi
- Aşağıdaki LaTeX paketleri (çoğu TeX Live full kurulumda gelir):
  - `fontspec`, `fontawesome5`, `roboto`, `sourcesanspro`
  - `geometry`, `fancyhdr`, `xcolor`, `hyperref`, `enumitem`

### Kurulum

<details>
<summary><b>macOS</b></summary>

```bash
brew install --cask mactex
```
</details>

<details>
<summary><b>Ubuntu / Debian</b></summary>

```bash
sudo apt install texlive-full
```
</details>

<details>
<summary><b>Windows</b></summary>

[MiKTeX](https://miktex.org/download) veya [TeX Live](https://tug.org/texlive/) kurun.
</details>

---

## 🎨 Özelleştirme

### Tema Rengi

`english_cv.tex` veya `turkish_cv.tex` içinde renk temasını değiştirebilirsiniz:

```latex
% Hazır renkler: russell-emerald, russell-skyblue, russell-red,
%   russell-pink, russell-orange, russell-nephritis, russell-concrete,
%   russell-darknight, russell-purple, russell-black
\colorlet{russell}{russell-emerald}

% Veya özel bir renk tanımlayın
\definecolor{russell}{HTML}{CA63A8}
```

### Bölüm Ekleme / Çıkarma

Ana `.tex` dosyasında `\input{...}` satırlarını yorum satırına alarak veya ekleyerek bölümleri kontrol edebilirsiniz:

```latex
\input{cv/education.tex}
\input{cv/experience.tex}
%\input{cv/summary.tex}      % Yorum satırı = devre dışı
```

### Yeni Deneyim Ekleme

`cv/experience.tex` (veya ilgili dosya) içinde şu formatı kullanın:

```latex
\cventry
  {Pozisyon}           % Pozisyon
  {Şirket Adı}        % Şirket
  {Şehir, Ülke}       % Konum
  {Başlangıç - Bitiş} % Tarih
  {
    \begin{cvitems}
      \item {Yaptığınız iş açıklaması.}
      \item {Bir diğer başarı veya sorumluluk.}
    \end{cvitems}
  }
```

---

## 🌐 Overleaf'te Kullanım

Bu şablonu Overleaf'te de kullanabilirsiniz:

1. Tüm dosyaları ZIP olarak indirin
2. [Overleaf](https://www.overleaf.com) → **New Project** → **Upload Project**
3. Derleyiciyi **XeLaTeX** olarak ayarlayın (Menu → Compiler)

---

## 📝 Lisans

Bu şablon [russell](https://github.com/posquit0/Awesome-CV) (Awesome-CV) temel alınarak oluşturulmuştur.

---

## 🤝 Katkıda Bulunma

1. Bu repo'yu fork'layın
2. Yeni bir branch oluşturun (`git checkout -b feature/yenilik`)
3. Değişikliklerinizi commit'leyin (`git commit -m 'Yeni bölüm eklendi'`)
4. Branch'inizi push'layın (`git push origin feature/yenilik`)
5. Pull Request açın
