![py.test](https://github.com/beaufortaml/company-ownership-example/workflows/py.test/badge.svg)

# Company ownership coding challenge

A small coding task that requires solving some simple tasks related to
the [norwegian share holder registry](https://www.altinn.no/starte-og-drive/skatt-og-avgift/skatt/aksjonarregisteret/).

For curious citizens, the full copy can be requested [here](https://www.skatteetaten.no/en/presse/aksjeeieropplysninger/).

Don't spend hours on this. It is voluntary. If you don't
feel comfortable that you can finish the assignment in a
reasonably short amount of time, don't worry.


## The application

The application is a simple REST api written in [flask](https://flask.palletsprojects.com/),
with a very simple local database used to store data in memory.

All application code is located in [app/main.py](app/main.py)

Three endpoints are defined:

* `/<orgnr>/owners`

  Returns all registered owners for a company.

  An **owner** is any entity (company _or_ person)
  that holds shares in the company.

* `/<orgnr>/holdings`

  Returns all registered holdings a company has in other
  companies.

  A **holding** means the number of/percentage of shares
  a person or company has in another company.

* /`<orgnr>/summary`

  Returns a basic summary of a company's ownership,
  as well as some other potentially interesting information.

  A company is thought to have an "interesting" ownership
  structure if there is a foreign entity among its owners.

  A company is also considered interesting if it has multiple
  share classes.


## Requirements

* Python 3


## Installing

* Clone this repo
* Install dependencies (`pip install -r requirements.txt`)


## Running

After installing dependencies, you can run the local development server:

```
$ python app/main.py
```

(assuming `python` points to your Python 3 interpreter)

The server is now running on [http://localhost:5000],
and you should be able to access the endpoints listed above.

If your operating system complains and tells you that
you can't run the application on port 5000 (`"Address in use"`
or some such), change the `SERVER_PORT` constant at the top
of the `main.py` file and try again.


## Testing

Most of the bundled tests are being skipped because they are not passing.
They should be fixed by changing the code in `main.py`, not by changing the tests!

To run the tests:

```
$ py.test
```

or

```
$ python -m pytest
```

(where `python` should be your Python 3 interpreter)

When all the code is working as expected, you will see pleasant, green dots.

When the code is not working as expected, you will see a scary, red wall of text.


## Solving

To make the application behave as it should, fill in the sections in
[app/main.py](app/main.py) that contain a `# TODO` comment.

At the top of this README is a banner that says `py.test passing`.
This is because there are a number of tests in the [tests/](tests)
folder that are being skipped (`@pytest.mark.skip(...)`).

Remove the `skip()` invocations, and run the tests. If all tests are
passing, you have a great success on your hands.


## Hints

* [flask](https://flask.palletsprojects.com/) is a lovely framework.
  By default, all flask responses have the status code `200`. To return
  a different response code, use `return <content>, <status_code>`.


## A note about Windows

If you are running Windows and you have issues running or testing
the application, we have no idea why. It is probably because you
are running Windows. Feel free to not complete the challenge.


## Help, I'm stuck and/or confused!

* Quit

or

* Send us an [lars+nospam@beaufort.io](email). We're happy to help.


## Submitting solutions

We would prefer if you fork the repo and show us a pull request,
but we're not picky. Anything goes.

Happy coding!
