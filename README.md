
Note: You can run ENQUIRE-Web by simply navigation to https://enquire-web.net. If you would like to host ENQUIRE-Web locally instead, please follow the instructions as specified in the rest of this README.

# Installation

Install conda environment as follows (there also exists a requirements.txt)
```bash
conda create --name enquire-web python=3.7
conda activate enquire-web
pip install celery Flask Flask-APScheduler flask-sqlalchemy Flask-WTF matplotlib mygene ndex2 networkx numpy pandas pcst-fast requests rq seaborn shortuuid WTForms pcst_fast
```

Installing Redis
```bash
MacOS: brew install redis

* For Windows and Linux operating systems, please refer to the official Redis documentation at: https://redis.io/docs/getting-started/installation/
```


# Hosting ENQUIRE-Web locally

1. First start redis server:
(Redis server has to be run before celery. Otherwise, celery will throw error.)
```bash
Simply type 'redis-server' on the terminal. (Redis runs on port 6379 by default)
```

2. Then start celery server:
```
Simply type 'celery -A app.celery worker --loglevel=info' on the terminal.

You should see a statement that says 'Connected to redis://localhost:6379/'
```

3. Finally, run the web app:
```
Type 'flask -A app.py --debug run' on the terminal.

Port: 5000 (that is, the web app can be accessed locally at: http://127.0.0.1:5000/)

We can change the port that the Flask app is running on by changing "app.run()" in app.py to "app.run(port='ENTER_DESIRED_PORT_NUMBER')".
```


# Citing ENQUIRE-Web

Please cite ENQUIRE-Web as follows:
- Will be updated once available.
