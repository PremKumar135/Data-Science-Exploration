FROM python:3.11-slim

WORKDIR /app

# Copy requirements file
COPY requirements.txt .

# Install dependencies using uv
RUN pip install uv
RUN uv venv
RUN uv pip install -r requirements.txt

# Copy application code
COPY weather_server.py .
COPY client_sse.py .

# Expose the port the server runs on
EXPOSE 8050

# Command to run the server
CMD ["uv", "run", "weather_server.py"] 