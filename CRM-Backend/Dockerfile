# FROM node:20-alpine

# WORKDIR /app

# COPY package.json package-lock.json ./
# RUN npm ci

# COPY prisma ./prisma
# RUN npx prisma generate

# COPY . .

# EXPOSE 3333

# CMD ["sh", "-c", "npx prisma db push && node prisma/ensureSeed.js && exec npm start"]

FROM node:20-alpine

WORKDIR /app

COPY package.json package-lock.json ./
RUN npm ci

COPY prisma ./prisma
RUN npx prisma generate

COPY . .

# Define a porta padrão local caso NENHUMA variável PORT seja passada pelo ambiente
ENV PORT=3333

# Opcional: apenas documentação
EXPOSE 3333

# Usa sh -c para garantir a execução sequencial dos scripts
CMD ["sh", "-c", "npx prisma db push && node prisma/ensureSeed.js && exec npm start"]