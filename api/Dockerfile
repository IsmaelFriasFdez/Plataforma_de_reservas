FROM node:22-alpine

WORKDIR /app

# Copiar dependencias de forma eficiente para aprovechar la caché
COPY package.json package-lock.json ./
RUN npm ci --omit=dev

# Copiar el resto del código
COPY . .

# Uso de usuario no root por seguridad
USER node

EXPOSE 3000

CMD ["node", "server.js"]