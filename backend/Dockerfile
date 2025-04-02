FROM python:3.11-slim

# Set environment variables to avoid interactive prompts
ENV DEBIAN_FRONTEND=noninteractive

# Set working directory
WORKDIR /app

# Copy and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy app source
COPY . .

# Variables d'environnement pour activer debug et reload
ENV FLASK_APP=app.py
ENV FLASK_ENV=development
ENV FLASK_RUN_RELOAD=true

# Exposer le port Flask
EXPOSE 5000

CMD ["flask", "run", "--host=0.0.0.0"]