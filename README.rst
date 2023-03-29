rssnotify
=========

``rssnotify`` is a simple rss feed parser that will execute arbitrary command when specific news are found.

Installation
============

.. code-block:: console

    $ pip install rssnotify

How To use rssnotify
====================
rssnotify use parameters from environment variables, create .env file and run rssnotify from the same directory:

.. code-block:: shell

    URLS=["https://www.kucoin.com/rss/news?lang=en"]
    KEYWORDS=["DELIST"]
    SINCE_HOURS=1
    COMMAND=["notify-send", "-t", "30000", "-u", "critical", "$TITLE", "$LINK"]

after than, you can run rssnotify in a cron job:

.. code-block:: shell

    13 * * * * bash -c "cd $HOME/.config/rssnotify ; XDG_RUNTIME_DIR=/run/user/$(id -u) rss-notify"
