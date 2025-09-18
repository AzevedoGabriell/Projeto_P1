FROM python:3.11-slim

# 1) Pasta de trabalho
WORKDIR /app

# 2) Dependências do sistema (opcional, boas para áudio/redes)
RUN apt-get update && apt-get install -y --no-install-recommends \
    libsndfile1 \
    && rm -rf /var/lib/apt/lists/*

# 3) Instalar requisitos da IA
COPY requirements.txt ./requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# 4) Copiar código da IA
COPY . .

# 6) Comando para manter o worker SEMPRE ligado
# Troque se seu entrypoint for outro arquivo/comando
CMD ["python", "interview.py", "prod"]
