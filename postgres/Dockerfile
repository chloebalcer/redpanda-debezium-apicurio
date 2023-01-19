FROM postgres:14

COPY data_import.sql /docker-entrypoint-initdb.d/

COPY pgconfig.conf /usr/share/postgresql/postgresql.conf.sample