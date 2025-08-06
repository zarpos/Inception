FROM debian:bookworm

# Instala MariaDB
RUN apt-get update && apt-get install -y mariadb-server && apt-get clean

# Copia el archivo de configuración (si lo tienes)
COPY /tools/50-server.cnf /etc/mysql/mariadb.conf.d/

# Copia el script de inicialización
COPY /tools/init-db.sh /docker-entrypoint-initdb.d/init-db.sh
RUN chmod +x /docker-entrypoint-initdb.d/init-db.sh

# Expon el puerto
EXPOSE 3306

# Usa el entrypoint oficial de MariaDB
CMD ["mysqld"]

