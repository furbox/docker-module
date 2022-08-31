FROM node:18-alpine3.15

# Set working directory
RUN mkdir -p /home/pokedex
WORKDIR /home/pokedex

# Copiar el directorio y su contenido
COPY . ./home/pokedex
COPY package.json tsconfig.json tsconfig.build.json /home/pokedex/
RUN yarn install --prod
RUN yarn build


# Dar permiso para ejecutar la applicación
RUN adduser --disabled-password pokeuser
RUN chown -R pokeuser:pokeuser /home/pokedex
USER pokeuser

# Limpiar el caché
RUN yarn cache clean --force

EXPOSE 3000

CMD [ "yarn","start:prod" ]