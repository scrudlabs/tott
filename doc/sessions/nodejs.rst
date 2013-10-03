JavaScript and NodeJS
=====================

Goals
-----

* Gain the ability to read and write JavaScript code
* Recognize the gotchas of JavaScript
* Know what `NodeJS`_ is
* Understand how to tap the NodeJS ecosystem
* Practice writing simple NodeJS applications
* Practice using the Node Package Manager (npm_)

Prep Materials
--------------

If time permits, try to review these resources before the meet-up. If you can't, come anyway.

* Skim `A Re-Introduction to JavaScript <https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript?redirectlocale=en-US&redirectslug=JavaScript%2FA_re-introduction_to_JavaScript>`_ (~20 minutes).
* Enter some of the code examples from the above page into `repl.it`_ and toy with them.
* Watch the TotT JavaScript screencast
* Read `The node.js Community is ... <http://caines.ca/blog/programming/the-node-js-community-is-quietly-changing-the-face-of-open-source/>`_ (~10 minutes)
* Watch the TotT JS Ecosystem screencast

Exercises
---------

You will need to complete the :doc:`/setup` instructions before you proceed with these exercises. Once you are set up, SSH into *tottbox* using the ``vagrant ssh`` command from the setup instructions. Then tackle the problems below. `Document what you find in a gist <https://gist.github.com/>`_ and share it in the `TotT community`_ later.

Guess a number
##############

Write a JS guessing game that picks a random, secret number between 1 and 100, lets the user take up to 5 guesses, and states if the secret number is equal to, higher, lower than a guess. Read input from stdin and print to stdout.

Guess a word
############

Install the American English word list in *tottbox* again if you have destroyed the VM since last using it. Remember, it installs into ``/usr/share/dict/words``.

.. code-block:: console

  sudo apt-get install wamerican

Now write a JavaScript program that chooses a random word from the list, reveals it one random letter at a time to the user, and asks the user to input guesses.

Read and visualize
##################

JSON is a lightweight, text-based, human-readable, open data exchange format. It is commonly used for communication between a web server backend and application frontend. It is also a valid subset of the JavaScript language.

Download `this list of U.S. capitals <https://gist.github.com/parente/6445329/raw/458d77a784246308388d68186027f0ad35cc6fc2/us-east-west.json>`_ to *tottbox*. The list is in JSON format with the capitals sorted east to west by longitude.

Write a JS program to compute the longitude distance between each capital and the next. Output the distances to stdout along with some summary stats for the entire dataset (e.g., min distance, max, mean, median, standard deviation). Try to find a creative way to represent the relative magnitude of the distances in your output.

Fetch a quote
#############

`I Heart Quotes <http://www.iheartquotes.com/>`_ provides a web service for fetching random quotations. You can test it by visiting http://www.iheartquotes.com/api/v1/random in your browser.

Write a JS program that pulls a quote from this site and displays it on stdout in the terminal. (Hint: Look at the `http module in the NodeJS standard library, particularly the request() function <http://nodejs.org/api/http.html#http_http_request_options_callback>`_).

Serve quotes
############

Write a tiny web server using the NodeJS ``http`` module that fetches a quote from `I Heart Quotes <http://www.iheartquotes.com/>`_ and returns it to the requesting client. Run the web server in *tottbox* on port 9000 and test it by pointing Google Chrome on your laptop to http://192.168.33.10:9000. (Hint: Google for or look on the NodeJS site for the few lines of code you need to create a web server in NodeJS. It's the example I gave at the start of class.)

Paint a rainbow
###############

Make a new directory in your shared *tottbox* folder. Change to that directory and use npm to install the ``colors`` module locally into that folder.

.. code-block:: console

    mkdir -p /vagrant/js/rainbow
    cd $!
    npm install colors

Google for ``nodejs colors``. Read about the features the module provides and view the examples. Now write a JS program that iterates over all the colors provided and outputs their names in their respective colors.

Show time til "freedom"
#######################

Make another folder and install the ``moment`` module using ``npm``. Look at the university calendar for the date that classes end this semester. Write a JS program using ``moment`` that output a human friendly description of the time left til classes end. (Hint: Look at ``moment.duration`` and its functions.)

Handle args
###########

In the same "freedom" folder, NPM install ``optimist``.  Find its documentation and study the examples. Now use it to add support for command line arguments that let the user specify:

#. The date of interest, with the end of semester date as the default.
#. If the output should be humanized or not, with yes, humanize, as the default.

Make it repeatable
##################

If you completed the two exerices directly above, your application now depends on ``moment`` and ``optimist``. Write a ``package.json`` file that installs these prerequisites when you type ``npm install``. (Hint: Refer to the interactive `package.json cheatsheet <http://package.json.nodejitsu.com/>`_).

Analyze sentiment
#################

Sentiment analysis is an attempt to determine subjective information from text. For example, identifying the *polarity* of a statement, whether it is a positive or negative opinion, has almost become synonymous with with "doing sentiment analysis."

Make another directory and install the ``natural`` NPM module. Find its documentation, read its summary, and focus on the section about classifiers.

Download the `sample movie reviews polariy dataset v2.0 <http://www.cs.cornell.edu/people/pabo/movie-review-data/>`_ and extract it in the folder you created:

.. code-block:: console

    cd /vagrant/whatever_folder_you_created
    wget http://www.cs.cornell.edu/people/pabo/movie-review-data/review_polarity.tar.gz
    tar xzf review_polarity.tar.gz

Spend a moment poking around in the contents of the extracted data. Then, write a JS program that reads in 50 positive reviews, 50 negative reviews, and trains a Naive Bayes classifier using them. Use the classifier example in ``natural`` as a guide. After training the classifier, test the classifier against a few more positive and negative examples from the dataset or your own custom test cases.

Explore common libs
###################

Use NPM to install the ``underscore`` and ``async`` modules, two very popular JavaScript libraries. Read their documentation. Come up with an example of where one or both might be effective. What do the alternatives look like? Why might you prefer use of these libraries?

Explore node_modules
####################

Install a bunch of modules using NPM. Poke around in the ``node_modules`` directory. Read about how NPM works on the web. What can you deduce about how NPM and NodeJS manage packages and their dependencies?

References
----------

  `Eloquent JavaScript <http://eloquentjavascript.net/>`_
    Introduction to programming in JavaScript

  `JavaScript on the Mozilla Developer Network <https://developer.mozilla.org/en-US/docs/Web/JavaScript>`_
    Comprehensive reference for all things JavaScript

  `NodeJS Docs <http://nodejs.org/api/>`_
    API reference for the NodeJS standard library