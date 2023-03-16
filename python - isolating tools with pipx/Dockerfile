FROM python:3.10.6-slim-buster

RUN apt-get update && \
    apt-get install -y python3-venv && \
    apt-get install -y pipx

ENV PATH="/root/.local/bin:$PATH"

RUN pipx install poetry==1.4.0 && \
    pipx install virtualenv==20.21.0

COPY isolating_tools_with_pipx /app/isolating_tools_with_pipx
COPY start.py /app/start.py
COPY poetry.lock /app/poetry.lock
COPY pyproject.toml /app/pyproject.toml
COPY README.md /app/README.md

WORKDIR /app/

RUN virtualenv .venv --python=3.10.6
ENV VIRTUAL_ENV=/app/.venv
ENV PATH="$VIRTUAL_ENV/bin:$PATH"

RUN poetry install --only main

CMD ["python", "start.py"]