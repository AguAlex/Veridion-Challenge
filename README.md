
# Company Classifier Using Sentence Embeddings 🤖

## Descriere

Acest proiect are ca scop clasificarea automata a unor companii (ml_insurance_challenge.csv) intr-un set predefinit de etichete (insurance_taxonomy.csv) folosind tehnici avansate de procesare a limbajului natural (NLP). Practic, atribuie fiecarei companii 3 etichete cele mai potrivite. Rezultatul se poate vedea in company_list_result.csv

## Despre implementare 🛠️

### 1. **Parsarea input-ului** 📋
   - Am combinat informatiile din fiecare coloana a fiecarei companii intr-o coloana noua pentru a crea un text care poate fi folosit pentru a obtine embeddings semantice.

### 2. **Incarcarea modelului NLP** 🧠
   - Am folosit **Sentence-Transformer** cu modelul `all-MiniLM-L6-v2`, un model de intelegere a limbajului natural care poate transforma propozitiile într-un **embedding numeric** (vector) care reprezinta semnificatia propozitiei respective intr-un spatiu semantic de dimensiune fixa.

### 3. **Generarea de embeddings pentru companii si etichete** 🧳
   - Am folosit **Sentence-Transformer** pentru a genera embeddings pentru fiecare companie din dataset, combinand informatiile lor.
   - De asemenea, am generat embeddings pentru fiecare label din taxonomy, astfel incat sa pot compara semantic companiile cu etichetele si sa aleg cele mai relevante etichete.

### 4. **Calcularea similaritatii intre companii si etichete** 📈
   - Am folosit **cosine similarity** pentru a calcula similaritatea semantica intre fiecare companie si toate etichetele din taxonomy.
   - Am selectat cele mai relevante 3 etichete pentru fiecare companie pe baza scorurilor de similaritate.

### 5. **Clasificarea si exportul rezultatelor** 🏷️
   - Am atribuit etichetele corespunzatoare fiecarei companii in baza scorurilor de similaritate si le-am adaugat intr-o coloana noua a dataset-ului.
   - Rezultatele finale au fost exportate intr-un nou fisier CSV (company_list_result.csv), care contine fiecare companie si etichetele sale asociate.
