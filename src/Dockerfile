FROM python:3.8-slim-buster

LABEL Author="Ricardo Brandao"

#Set working directory from now on we will be inside /app
WORKDIR /app

#Copy packages files and install them
COPY requirements.txt ./
RUN python -m pip install -r requirements.txt

#Copy the remaining items
COPY . .

EXPOSE 5000

CMD ["gunicorn", "--workers=3", "--bind", "0.0.0.0:5000", "app:app"]