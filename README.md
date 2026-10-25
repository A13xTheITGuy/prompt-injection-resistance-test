# 🛡️ Prompt Injection Resistance Test

## 🇬🇧 English

This project represents the solution to **Challenge 3C** from the *AI Agent-Based Application Development* course (4th Year, 7th Semester). Its purpose is to evaluate the robustness of a system prompt against *prompt injection* attacks (direct and indirect) and to demonstrate their limitations.

## 🎯 Objectives

- Defining a technical support assistant (TaskManager) with 3 verifiable restrictions.
- Testing 20 messages (5 legitimate, 5 off-topic, 5 direct attacks, 5 indirect attacks).
- Measuring the differences between a basic system prompt (v1) and a secured one (v2).
- Demonstrating the need to move certain critical rules from the prompt into code.

## 🛠️ Technology Stack

- **Language:** C# (.NET 10)
- **Frameworks & SDKs:**
  - `Microsoft.Agents.AI` (Microsoft Agent Framework)
  - `Microsoft.Extensions.AI` (`IChatClient` interface)
  - `Azure.AI.OpenAI` (official Azure SDK)
- **Model:** `gpt-4.1-mini` (implemented through Azure AI Foundry)
- **Measurement:** `Microsoft.ML.Tokenizers` (for exact token counting)

## 📊 Key Results

- **v1 (Basic Prompt):** 2 violations (both from indirect attacks).
- **v2 (Secured Prompt):** 2 violations, but introduced 1 excessive refusal (the price of safety).
- **Conclusion:** The system prompt is not sufficient. Indirect attacks (instructions hidden in text) bypass the prompt's rules and require filters at the code or platform level (e.g., the Azure filter automatically blocked test 11).

## 🚀 How to Run Locally

To run this project, you need an Azure OpenAI deployment for the `gpt-4.1-mini` model.

1. Clone the repository:
   ```
   git clone https://github.com/A13xTheITGuy/prompt-injection-resistance-test.git
   ```
2. Set the environment variables for the endpoint and API key:
   - AZURE_OPENAI_ENDPOINT
   - AZURE_OPENAI_API_KEY
3. Run the project:
   ```
   dotnet run
   ```
4. The results will be generated in the `test_results.json` file.

---

*Project developed by A13xTheITGuy | Universitatea Politehnica Timișoara, 4th Year.*

<br>

## 🇷🇴 Română

Acest proiect reprezintă rezolvarea **Provocării 3C** din cadrul cursului *Dezvoltarea aplicațiilor bazate pe agenți AI* (Anul IV, Semestrul 7). Scopul său este de a evalua robustețea unui system prompt împotriva atacurilor de tip *prompt injection* (directe și indirecte) și de a demonstra limitele acestora.

## 🎯 Obiective

- Definirea unui asistent de suport tehnic (TaskManager) cu 3 interdicții verificabile.
- Testarea a 20 de mesaje (5 legitime, 5 off-topic, 5 atacuri directe, 5 atacuri indirecte).
- Măsurarea diferențelor dintre un system prompt de bază (v1) și unul securizat (v2).
- Demonstrarea necesității mutării unor reguli critice din prompt în cod.

## 🛠️ Stack Tehnologic

- **Limbaj:** C# (.NET 10)
- **Framework-uri & SDK-uri:**
  - `Microsoft.Agents.AI` (Microsoft Agent Framework)
  - `Microsoft.Extensions.AI` (Interfața `IChatClient`)
  - `Azure.AI.OpenAI` (SDK-ul oficial Azure)
- **Model:** `gpt-4.1-mini` (implementat prin Azure AI Foundry)
- **Măsurare:** `Microsoft.ML.Tokenizers` (pentru numărarea exactă a tokenilor)

## 📊 Rezultate cheie

- **v1 (Prompt de bază):** 2 încălcări (ambele la atacuri indirecte).
- **v2 (Prompt securizat):** 2 încălcări, dar a introdus 1 refuz excesiv (prețul siguranței).
- **Concluzie:** System prompt-ul nu este suficient. Atacurile indirecte (instrucțiuni ascunse în text) trec de regulile promptului și necesită filtre la nivel de cod sau platformă (ex: filtrul Azure a blocat automat testul 11).

## 🚀 Cum se rulează local

Pentru a rula acest proiect, ai nevoie de un deployment Azure OpenAI pentru modelul `gpt-4.1-mini`.

1. Clonați repository-ul:
   ```
   git clone https://github.com/A13xTheITGuy/prompt-injection-resistance-test.git
   ```
2. Setați variabilele de mediu pentru endpoint și cheie:
   - AZURE_OPENAI_ENDPOINT
   - AZURE_OPENAI_API_KEY
3. Rulați proiectul:
   ```
   dotnet run
   ```
4. Rezultatele vor fi generate în fișierul `test_results.json`.

---

*Proiect realizat de A13xTheITGuy | Universitatea Politehnica Timișoara, Anul IV.*
