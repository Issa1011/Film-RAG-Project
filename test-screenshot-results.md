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





