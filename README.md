# Film RAG Project
## Om projektet

Jeg har lavet en AI-agent, som kan svare på spørgsmål om film. Agenten bruger RAG (Retrieval-Augmented Generation), som betyder, at den kan finde information i en database og bruge den til at svare på spørgsmål.

Jeg har arbejdet med både Vector RAG og Graph RAG, som er to forskellige måder at finde information på. 

### Teknologier jeg har brugt
- n8n: Til at bygge min AI-agent og forbinde de forskellige dele.
- Ollama: Til at køre AI-modeller lokalt på min computer.
- Llama 3.2: AI-modellen, der bruges til at svare på spørgsmål.
- nomic-embed-text: Til at lave tekst om til tal (embeddings), så AI'en kan søge efter lignende information.
- Neo4j: En grafdatabase, hvor jeg har gemt film og deres oplysninger.
- Qdrant: En vektordatabase, som bruges til at finde film ud fra deres indhold.
- Docker: Til at køre de forskellige programmer lokalt.

### Hvordan virker det?
1. Brugeren skriver et spørgsmål om en film til AI-agenten.
2. AI-agenten finder ud af, hvilke oplysninger den skal bruge.
3. Vector RAG kan finde film, der minder om det, brugeren søger efter.
4. Graph RAG kan finde konkrete oplysninger om film i Neo4j
5. AI-agenten bruger oplysningerne til at svare på spørgsmålet.

### Hvad kan min AI-Agent?
- Svare på spørgsmål om film.
- Finde film ud fra beskrivelser og lignende indhold.
- Hente oplysninger fra Neo4j.
- Søge efter information med Vector RAG.
- Bruge både Vector RAG og Graph RAG til at finde svar.

### Status
Jeg har bygget min AI-Agent i n8n og fået mine workflows til at fungere.

Jeg har også arbejdet med at gemme filmi Neo4J og lave embeddings, så filmene kan bruges til søgning. 
