FROM node:18.14.2
WORKDIR /app

# Manter os pakages em cima do NPM install, entrega
# somente os arquivos necessários para ele rodar,
# mantendo estas informações no cache.
COPY package*.json ./ 
RUN npm install

# Somente após isso, é copiado o restante dos arquivos, desta forma, o cache é utiizado novamente, caso não seja
# alterado os pacotes, não sendo necessário fazer o download e instalção completa do NPM novamente.
COPY . .
CMD ["node", "server.js"]