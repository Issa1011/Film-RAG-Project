#### Test 1 – Graph RAG
**Spørgsmål:** Hvem har instrueret Interstellar?

**Værktøj:** Film - Graph Retrieval.

**Hentede oplysninger:** AI-agenten hentede oplysninger om film og instruktører fra Neo4j.

**Resultat:** Agenten svarede korrekt, at Christopher Nolan har instrueret Interstellar, men nævnte også Titanic, hvilket er forkert.

<img width="2048" height="1342" alt="image" src="https://github.com/user-attachments/assets/2fbd8898-381e-43a6-a791-988ead9f749e" />


#### Test 2 – Vector RAG
**Spørgsmål:** Kan du anbefale en romantisk film med en tragisk kærlighedshistorie?

**Værktøj:** Film - Vector Retrieval Tool.

**Hentede oplysninger:** Agenten brugte Vector Retrieval til at søge efter film i Neo4j ved hjælp af embeddings. Den anbefalede Titanic.

**Resultat:** Agenten anbefalede Titanic (1997) og forklarede, hvorfor filmen passer til spørgsmålet.

**Vurdering:** Testen var vellykket. Vector RAG blev brugt, og anbefalingen passede til brugerens beskrivelse.

<img width="2048" height="1282" alt="image" src="https://github.com/user-attachments/assets/7e2be500-4e0a-4d81-90ec-edd5b099153f" />

#### Test 3 – Kombination af Graph og Vector RAG
**Spørgsmål:** Kan du anbefale en science fiction-film om rummet og fortælle, hvem der har instrueret den?

**Værktøjer:** Graph Retrieval og Vector Retrieval.

**Hentede oplysninger:** Agenten brugte Vector Retrieval til at finde en relevant film og Graph Retrieval til at hente oplysninger om instruktøren.

**Resultat:** Agenten anbefalede Avatar (2009) og fortalte, at James Cameron har instrueret filmen.

**Vurdering:** Begge værktøjer blev brugt uden fejl. Testen viser, at AI-agenten kan kombinere Vector RAG og Graph RAG. 

<img width="2048" height="1282" alt="image" src="https://github.com/user-attachments/assets/e46ac4f5-98e2-4bb2-9360-43f76b93f381" />




