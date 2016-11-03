Tip4commit
==========

[![tip for next commit](https://tip4commit.com/projects/307.svg)](https://tip4commit.com/projects/307)
[![Build Status](https://travis-ci.org/tip4commit/tip4commit.svg?branch=master)](https://travis-ci.org/tip4commit/tip4commit)

Donate emercoin to open source projects or receive tips for code contributions.

Name | Link
----|----|
Official site | https://tip4commit.com/
Discussions | https://bitcointalk.org/index.php?topic=31580
FAQs | https://github.com/tip4commit/tip4commit/wiki/FAQ
Issues | https://github.com/tip4commit/tip4commit/issues

Installation
============

To run emc4commit in development mode follow these instructions:

* Install [Ruby](https://www.ruby-lang.org/en/downloads/) 1.9+

* Install the [bundler](http://bundler.io/) gem (you may need root):
```
gem install bundler
```

* Install [git](http://git-scm.com/downloads)

* Clone the repository
```
git clone git@github.com:sigmike/emc4commit.git
cd emc4commit
```

* Install the sqlite3 development libraries

* Install the gems (without the production gems):
```
bundle install --without mysql postgresql
```

* Create `database.yml`.
```
cp config/database.yml{.sample,}
```

* Create `config.yml`
```
cp config/config.yml{.example,}
```

* Edit `config.yml`

* Initialize the database
```
    bundle exec rake db:migrate
```

* Make sure `ppcoind` is running with RPC enabled

* Run the server


    bundle exec rails server

* Connect to the server at http://localhost:3000/


To update the project balances run this command:
```
    bundle exec rails runner "BalanceUpdater.work"
```

To retreive commits and send tips on project that do not hold tips:
```
    bundle exec rails runner "BitcoinTipper.work"
```

tip4commit Development
======================

If you would like to contribute to the development of tip4commit, you can find the contribution guidelines and installation instructions in the [developer README](https://github.com/tip4commit/tip4commit/wiki/Developer-README)


License
=======

[MIT License](https://github.com/tip4commit/tip4commit/blob/master/LICENSE)
