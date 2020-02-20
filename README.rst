sqlalchemy-vertica-python
=========================

NOTE: As of February 2020, The most up-to-date fork is being maintained `here <https://github.com/bluelabsio/sqlalchemy-vertica-python/>`_. Please direct all contributions to that repository.

Vertica dialect for sqlalchemy. Forked from the `Vertica ODBC dialect <https://pypi.python.org/pypi/vertica-sqlalchemy>`_.

This module implements a Vertica dialect for SQLAlchemy using `vertica-python <https://github.com/uber/vertica-python>`_. Engine creation: 

.. code-block:: python

    import sqlalchemy as sa
    sa.create_engine('vertica+vertica_python://user:pwd@host:port/database')

Installation
------------

From PyPI: ::

     pip install sqlalchemy-vertica-python

From git: ::

     git clone https://github.com/LocusEnergy/vertica-sqlalchemy 
     cd vertica-sqlalchemy
     python setup.py install
     

Usage
------------

**ID/Primary Key Declaration**

Do not use this. The INSERT will fail as it will try to insert the ID

    id = Column(Integer, primary_key=True)

Do the following instead

    id = Column(Integer, Sequence('user_id_seq'), primary_key=True)
