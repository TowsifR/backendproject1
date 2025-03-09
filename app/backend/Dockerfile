FROM python:3.12-slim

WORKDIR /app/backend

RUN pip install poetry


COPY pyproject.toml poetry.lock /app/backend/


##Install dependencies 
RUN poetry install --no-root
#
##Copy backend folder
COPY . /app/backend
#
WORKDIR /app/backend/api
#

EXPOSE 8000

CMD ["poetry", "run", "uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000" ]