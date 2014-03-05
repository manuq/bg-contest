Sugar Background Image Contest
==============================

This is the web application for the contest.

Development
-----------

1. If you don't have virtualenv:

    ```
    sudo easy_install virtualenv
    ```

    Or
    ```
    sudo pip install virtualenv
    ```

    Or
    ```
    sudo apt-get install python-virtualenv
    ```

2. Create environment:

    ```
    virtualenv venv
    . venv/bin/activate
    pip install -r requirements.txt
    mkdir media
    chmod a+rwx media
    ```

3. Create database:
    ```
    python -c "from __init__ import init_db; init_db()"
    ```

    Or
    ```
    sqlite3 contest.db < schema.sql
    ```

4. Start:

    ```
    python __init__.py
    ```



5. In another console, serve media:

    ```
    cd media
    python -m SimpleHTTPServer
    ```

Deployment
----------

Pay attention to all the comments in `__init.py__` that start with #FIXME PROD

Translations
------------

To add a new language, run (example with 'es'):

    pybabel init -i translations/messages.pot -d translations -l es

To add translatable strings

1. add these tags around the text: `{% trans %}text here{% endtrans %}`.

2. run `./babel_extract.sh`

3. edit the po files with a po editor

4. run `./babel_compile.sh`
