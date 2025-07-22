# Predikcija kvaliteta kafe uz pomoć veštačke inteligencije

Ovaj projekat je rađen u okviru predmeta Primena veštačke inteligencije na Fakultetu organizacionih nauka.  
Koristi modele dubokog učenja za klasifikaciju kvaliteta kafe na osnovu njenih hemijskih osobina, porekla i načina obrade.
Cilj projekta je predikcija ocene kvaliteta kafe na osnovu hemijskih karakteristika, visine nadmorske visine, regiona porekla i tipa obrade.

---

## Tehnologije koje su korišćene

- Python 3 (Google Colab)
- Pandas, NumPy – obrada podataka
- Scikit-learn (`train_test_split`, `StandardScaler`) - evaluacija modela
- TensorFlow / Keras - izrada neuronske mreže
- Matplotlib - vizualizacija
- Dataset: [Arabica Coffee Data](https://github.com/jldbc/coffee-quality-database)
- Transformers / BERT (LLM) – za obradu tekstualnih podataka

---

## Koraci u projektu

1. **Učitavanje i čišćenje podataka**  
2. **Klasifikacija ocene kvaliteta** (loša / srednja / vrhunska)
3. **One-hot enkodiranje i normalizacija**
4. **Podela na trening (60%) i test (40%) skup**
5. **Treniranje Dense neuronske mreže (128 → 64 → 3 softmax)**
6. **Evaluacija modela i crtanje grafikona**
7. **Korišćenje BERT embeddinga za tekstualne kolone**
8. **Čuvanje modela i eksport rezultata**

----

## Model

Model je konstruisan kao neuronska mreža sa sledećim slojevima:

- Dense(128) + ReLU
- Dropout(0.3)
- Dense(64) + ReLU
- Output Dense(3) + Softmax

---

## Evaluacija

Model je treniran na one-hot enkodiranim i normalizovanim podacima.  
Tačnost na test skupu je iznosila oko **14–15%**, što ukazuje na potrebu za daljom optimizacijom kroz balansiranje klasa i redukciju dimenzionalnosti.

- Korišćena funkcija gubitka: `BinaryCrossentropy`
- Prikazane metrike: `accuracy`, `confusion matrix`, `classification report`

---

## Sadržaj repozitorijuma

- `Predikcija_kvaliteta_kafe.ipynb` – glavni kod projekta
- `model_kvalitet_kafe.h5` – sačuvani model
- `predikcije_kafe.csv` – predikcije na test skupu

---

## Pokretanje

Za pokretanje projekta koristi:
- [Google Colab](https://colab.research.google.com/)
- ili lokalno Jupyter okruženje sa instaliranim `tensorflow`, `pandas`, `sklearn`, `matplotlib`

---

## Autor

Marija Milić
