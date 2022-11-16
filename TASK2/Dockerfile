FROM python:3.10

COPY . requirements.txt /smart_home
RUN pip3 install --no-cache-dir --upgrade -r /smart_home/requirements.txt

COPY ./smart_home /smart_home
RUN python3 /smart_home/manage.py makemigrations
RUN python3 /smart_home/manage.py migrate

EXPOSE 8000

WORKDIR smart_home

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

