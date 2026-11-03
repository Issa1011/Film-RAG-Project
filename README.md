# Film RAG Project
## Om projektet

Jeg har lavet en AI-agent, som kan svare på spørgsmål om film. Agenten bruger RAG (Retrieval-Augmented Generation), som betyder, at den kan finde information i en database og bruge den til at svare på spørgsmål.

Jeg har arbejdet med både Vector RAG og Graph RAG, som er to forskellige måder at finde information på. 

### Teknologier jeg har brugt
- n8n: Til at bygge min AI-agent og forbinde de forskellige workflows.
- Ollama: Til at køre AI-modeller lokalt på min computer.
- Llama 3.2: AI-modellen, der bruges til at forstå spørgsmål og formulere svar.
- nomic-embed-text: Til at omdanne tekst til embeddings, så jeg kan finde film med lignende indhold.
- Neo4j: Til at gemme film, instruktører, skuespillere og deres relationer. Jeg bruger også Neo4j som vektordatabase til at gemme embeddings og søge efter lignende film.
- Qdrant: En vektordatabase, som jeg har arbejdet med under udviklingen, men som ikke bruges i min endelige AI-agent.
- Docker: Til at køre programmerne lokalt på min computer.

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

### Mine workflows
Jeg har lavet fire workflows i n8n, som arbejder sammen med Neo4j og Ollama.
- Film - AI Agent: Min chatbot, som modtager spørgsmål fra brugeren og vælger, hvilket søgeværktøj der skal bruges.
- Film - Graph Retrieval: Finder oplysninger om film, instruktører og skuespillere ved at søge i relationerne i Neo4j.
- Film - Vector Retrieval Tool: Bruger embeddings til at finde film, der passer til brugerens beskrivelse.
- Film - Vector search: Mit første Vector RAG-workflow, hvor jeg testede, hvordan man finder lignende film og får Llama 3.2 til at lave anbefalinger.

### Hvordan hænger de sammen?
Når brugeren stiller et spørgsmål, modtager AI-agenten spørgsmålet og vælger et søgeværktøj.

Graph Retrieval bruges til konkrete oplysninger om film og personer. Vector Retrieval bruges til at finde film med lignende indhold eller temaer.

Begge værktøjer henter oplysninger fra Neo4j. Derefter bruger AI-agenten Llama 3.2 til at formulere et svar på dansk.

### Workflow-filer
Alle fire workflows ligger som JSON-filer i dette GitHub-repository. De kan importeres i n8n.
