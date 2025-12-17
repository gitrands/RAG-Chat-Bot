#### 1. Start the Database
Open your terminal, navigate to the project folder, and start the Docker container.

```bash
cd /home/jeeva/Documents/Gen-AI-projects/ai-rag-chatbot-ollama-postgres-docker-main
docker compose up -d db
```

#### 2. Ensure Ollama is Running
Make sure the Ollama service is active.

```bash
ollama serve
```
*(If it says "address already in use", it means it's already running in the background, which is good).*

#### 3. Start the Chatbot Server
Navigate to the src directory and run the application.

```bash
cd src
python main.py
```
*You should see `* Serving Flask app 'main'` and `* Running on http://127.0.0.1:8000`.*

#### 4. Test the Chatbot
Open a **new terminal window** and run this command to chat:

```bash
curl -X POST http://localhost:8000/api/v1/Alfred/Chat \
-H "Content-Type: application/json" \
-d '{"Question": "Can I clone a VM?"}'

