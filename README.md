# nudge-matcher

Matching algo service for Sophia

## Requirements

- Docker: https://www.docker.com
- docker-compose: https://github.com/docker/compose
- this repo: `git clone https://github.com/Nudge-Technologies/nudge-matcher`

## Running

Run this anytime you need to start/restart the dev server: `docker-compose up --build`

To shutdown jupyter and the test database do `Ctrl+C` in the terminal where you ran the command above

## Connect to the database

```python
from sqlalchemy import create_engine
import os
engine = create_engine(os.environ["DATA_URL"])
```

Once you're conneted to the DB you can start maniplating the data with SQLAlchemy and/or Pandas.

SQLAlchemy tutorials: https://www.sqlalchemy.org/library.html#tutorials

## Test data

If you need to populate the database with some sample data open up a new terminal in Jupyter and run:

```bash
PGPASSWORD=password pg_restore -C -d postgres -h database -U nudge ./scripts/seed.sql
```

## Folder structure

`notebooks` - for Jupyter experiments, you can put anything you want here

`src` - for production code, try to keep it clean :)

## Installing packages

If you need to add production dependencies, open a terminal on your **host** and run:

```bash
pipenv install packagename
```

Then restart the dev server.
