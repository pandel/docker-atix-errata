Docker compose for ATIX AG errata_server and errata_parser
---------------------------------------------

------

### Prerequisites:

Install the latest Docker release to your server.

Get the source code for ATIX AG [`errata_server`](https://github.com/ATIX-AG/errata_server) and [`errata_parser`](https://github.com/ATIX-AG/errata_parser) and build the Docker images according to their description.
In short:

```bash
# Build errata_parser image
git clone https://github.com/ATIX-AG/errata_parser
cd errata_parser
docker build -t errata_parser:latest .
cd ..

# Build errata_server image
git clone https://github.com/ATIX-AG/errata_server
cd errata_server
docker build -t errata_server:latest .
cd ..

# Now clone this repository here
git clone https://github.com/pandel/docker-atix-errata
cd docker-atix-errata
```

### How to start everything:

1. Copy `env-example` to `.env`
2. (Optional) Adjust errata_parser schedule in `.env`, see [ofelia documentation](https://github.com/mcuadros/ofelia) for more information
3. Copy `default_config.json` to `config.json`
4. (Optional) Adjust distribution and release data you want to fetch in `config.json`, see [errata_parser documentation](https://github.com/ATIX-AG/errata_parser) on how to reconfigure everything / for Ubuntu: leave `ubuntu` AND `ubuntu-esm` in your `config.json`, or you will have to change `compose-ubuntu.yml` accordingly
5. According to the data you want to fetch, copy one of the following compose files to `compose.yml`:
   - `compose-all.yml`: get all available data for Debian, Ubuntu and Ubuntu-esm
   - `compose-debian.yml`: get Debian data only
   - `compose-ubuntu.yml`: get Ubuntu and Ubuntu-Esm data only

Now startup your compose stack like this:

`docker compose up -d`

If you want to see some log data directly after starting up, you can also do it like this:

`docker compose up -d && docker compose logs -f`

If you have seen enough, exit the log display with `STRG-C`

