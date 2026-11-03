## Opsætning af Film RAG Project
#### Programmer
Projektet er bygget lokalt med:
- Docker
- n8n
- Ollama
- Neo4j

#### AI-modeller
Jeg bruger to modeller gennem Ollama:
- llama3.2: Bruges til at forstå spørgsmål og formulere svar.
- nomic-embed-text: Bruges til at lave embeddings med 768 dimensioner.

#### Database
Jeg bruger Neo4j til både Graph RAG og Vector RAG.
Databasen indeholder 10 film samt oplysninger om instruktører og skuespillere.

Jeg har brugt følgende noder:
- Film: Indeholder filmtitel og embedding.
- Person: Indeholder personens navn.

Og følgende relationer:
- DIRECTED: Forbinder en instruktør med en film.
- ACTED_IN: Forbinder en skuespiller med en film.

Databasen indeholder:
- 10 Film-noder
- 19 Person-noder
- 17 ACTED_IN-relationer
- 10 DIRECTED-relationer
- I alt 29 noder og 27 relationer

#### Vector RAG
Jeg har lavet embeddings af filmene ved hjælp af nomic-embed-text.

Hver embedding indeholder 768 tal.

I Neo4j har jeg oprettet et vector index med navnet film_embeddings, som bruges til at finde film med lignende indhold.

#### Graph RAG
Jeg har oprettet relationer mellem film, instruktører og skuespillere i Neo4j.
AI-agenten kan bruge disse relationer til at besvare spørgsmål om eksempelvis, hvem der har instrueret en bestemt film.

#### Sådan køres projektet
1. Start Docker, Neo4j, n8n og Ollama.
2. Sørg for, at modellerne llama3.2 og nomic-embed-text er installeret i Ollama.
3. Opret filmdata, relationer, embeddings og vector index i Neo4j.
4. Importér JSON-filerne fra mappen workflows i n8n.
5. Tilpas forbindelserne til Ollama og Neo4j.
6. Åbn workflowet Film - AI Agent, og stil et spørgsmål i chatten.

#### Eksempel på filmdata:
Et eksempel fra min Neo4j-database er filmen Inception:
- Titel: Inception
- År: 2010
- Genre: Science Fiction
- Beskrivelse: En tyv kan trænge ind i menneskers drømme og stjæle hemmeligheder.
- Embedding: 768 tal genereret med nomic-embed-text.
Filmene indeholder oplysninger, som AI-agenten bruger til at finde relevante film gennem Vector RAG.

#### Vector Index i Neo4j:
Jeg har oprettet et Vector Index til at søge efter film ud fra deres betydning og indhold.
- Navn: film_embeddings
- Type: VECTOR
- Node: Film
- Property: embedding
- Antal film i indekset: 10
- Status: ONLINE
- Embedding-dimensioner: 768
Indekset bruges af Vector RAG til at finde film, der passer til brugerens spørgsmål-

### Oprettelse af Vector Index
Følgende Cypher-kommando kan bruges til at oprette et Vector Index i Neo4j med 768 dimensioner og cosine similarity:

CREATE VECTOR INDEX film_embeddings IF NOT EXISTS FOR (f:Film) ON (f.embedding) OPTIONS {indexConfig: {vector.dimensions: 768, vector.similarity_function: 'cosine'}};

