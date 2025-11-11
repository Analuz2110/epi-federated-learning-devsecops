FROM python:3.10-slim

WORKDIR /app

COPY requirements.txt .

# Instala dependências do sistema necessárias para OpenCV
RUN apt-get update && apt-get install -y \
    libgl1 \
    libglib2.0-0 \
    libopencv-dev \
    && pip install --no-cache-dir -r requirements.txt

# Copia os arquivos do cliente
COPY fl_client.py .
COPY detector.py .
COPY frame_receiver.py .

# Comando pra rodar o container
CMD ["python", "frame_receiver.py"]
