Application Structure:
  - Project Folder/
     - app/
       - static/
       - templates/
       - main.py
       - uwsgi.ini
       - wsgi.py
     - Dockerfile
     - requirements.txt

Preparation:
  - requirements.txt:
    - Use "pip freeze > requirements.txt" to export your installed environment packages.
  - wsgi.py:
    ```
    from main import app as application

    if __name__ == "__main__":
        application.run()
    ```
  - uwsgi.ini:
    ```
    [uwsgi]
    module = wsgi

    http = 127.0.0.1:8080

    master = true
    processes = 5

    vacuum = true
    enable-threads = true
    thunder-lock = true

    die-on-term = true
    ```
