Docker compose for ATIX AG Errata Server and Parser
=========================================================

------

How to start everything:
---------------

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

