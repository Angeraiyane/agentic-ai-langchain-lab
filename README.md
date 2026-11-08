# Agentic AI — LangChain & LangGraph Lab

Ce projet regroupe les travaux pratiques sur la conception et le déploiement d'agents autonomes à l'aide de l'écosystème LangChain et LangGraph, en privilégiant des alternatives gratuites et open source pour l'inférence et les embeddings.

## 🚀 Fonctionnalités couvertes

- **Agents Simples & Dynamic Model Routing :** Routage dynamique du modèle via middleware (`@wrap_model_call`) selon l'environnement (`test` vs `prod`).
- **Persistance & Mémoire :** Gestion des états conversationnels avec checkpoints mémoire (`InMemorySaver`) et bases relationnelles.
- **Outillage d'Agents (Tools) :**
  - Outils sur-mesure (météo, RH, recherche Web DuckDuckGo).
  - Exécution sécurisée de code via `PythonREPLTool` (calculs symboliques et numériques).
  - RAG intégré sous forme d'outil (`create_retriever_tool`) adossé à un index vectoriel FAISS local.
- **Contrôle & Garde-fous (Guardrails) :**
  - Détection et anonymisation de données sensibles (PII : cartes bancaires, e-mails, clés API).
  - Validation déterministe pré-agent (mots-clés interdits) et validation post-agent basée sur un LLM de sécurité.
  - Intervention humaine dans la boucle (*Human-in-the-loop*) avec suspension et reprise d'exécution sur approbation.

## 🛠️ Stack Technique

- **Langage :** Python 3.11+
- **Gestionnaire de dépendances :** `uv`
- **Orchestration d'agents :** LangChain 0.3+, LangGraph
- **LLM Provider :** Groq API (Llama 3.3 / Llama 3.1) / Modèles locaux
- **Embeddings & Vector Store :** HuggingFace (`sentence-transformers/all-MiniLM-L6-v2`), FAISS