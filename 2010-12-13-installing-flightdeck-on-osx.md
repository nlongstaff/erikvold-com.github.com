---
title: Installing FlightDeck on OSX
short URL: http://r.evold.ca/flightdeck-osx
tags: FlightDeck, Mozilla, Jetpack
---
I had a very difficult time trying to setup <a title="Mozilla FlightDeck" rel="external" rev="vote-for" target="_blank" href="https://github.com/zalun/FlightDeck">FlightDeck</a> locally for development when I tried months ago, partly because I couldn't find documentation that walked me all of the way through setting it up, and also partly due to the fact that I'm so new to Python. So one of my personal goals for the Mozilla all hands work week was to seek help from <a title="Piotr Zalewa" target="_blank" rel="external" rev="vote-for" href="http://piotr.zalewa.info/">Piotr Zalewa</a> (aka Zalun) on how to install FlightDeck on my macbook. Well he was very kind and helped me out, and now I've got FlightDeck running locally! so I thought I would document what I did as best I can so that I don't forget this information, and so that I can share it with you.
</p>

<h2>Requirements (for these instructions)</h2>
<ul>
  <li>OSX</li>
  <li>Python 2.6</li>
  <li>Git</li>
  <li>MySQL</li>
</ul>

<h2>Installation</h2>

<div class="code">$ cd /www/<br>
$ git clone <a target="_blank" href="https://github.com/zalun/FlightDeck.git">https://github.com/zalun/FlightDeck.git</a><br>
$ cd FlightDeck<br>
$ sudo easy_install pip<br>
$ sudo pip install virtualenvwrapper</div>

<p>Now add the following to ~/.bash_profile</p>

<div class="code">export WORKON_HOME=~/Envs<br>
source /usr/local/bin/virtualenvwrapper.sh</div>


<p>Then close your terminal instance and start a new one, then type to following commands:</p>

<div class="code">$ cd /www/FlightDeck<br>
$ sudo pip install virtualenv<br>
$ mkvirtualenv --no-site-packages flightdeck</div>

<p>Now you are in a virtual environment called "flightdeck", when you want to return to this virtual environment later on remember to use 'workon flightdeck'.</p>

<p>Now you need to install the required dependencies, to do so to the following:</p>

<div class="code">$ pip install simplejson<br>
$ pip install mysql-python<br>
$ pip install -r ./requirements/development.txt</div>

<p>Now you'll need to create a new settings_local.py file in the root (where settings.py can be found):</p>

<div class="code">from settings import  *<br>
<br>
PRODUCTION = False<br>
DEBUG = True<br>
SESSION_COOKIE_SECURE = False<br>
<br>
DATABASES = {<br>
    'default': {<br>
        'NAME': 'flightdeck-db',<br>
        'ENGINE': 'django.db.backends.mysql',<br>
        'HOST': '127.0.0.1',<br>
        'PORT': '',<br>
        'USER': 'root',<br>
        'PASSWORD': '*****',<br>
    },<br>
}</div>

<p><strong>Note:</strong> you need to create a new MySQL db called 'flightdeck-db' (or whatever you want it to be).</p>

<p>Then type the following:</p>

<div class="code">$ ./manage.py syncdb</div>

<p>
When you are asked "Would you like to create one now? (yes/no):" then type "yes" and follow the instructions from there.
</p>

<div class="code">$ git submodule init<br>
$ git submodule update<br>
$ ./manage.py add_core_lib addon-sdk-0.9<br>
$ ./manage.py runserver</div>

<p>Now you're done! and FlightDeck should be running locally now (you should see a message that says something like "Development server is running at http://127.0.0.1:8000/")</p>

<p>
When you want to shutdown the server go to the terminal window and hit ctrl+c.
</p>

<p>
The next time that you want to run the server do this:
</p>

<div class="code">$ cd /www/FlightDeck<br>
$ workon flightdeck<br>
$ ./manage.py runserver</div>
