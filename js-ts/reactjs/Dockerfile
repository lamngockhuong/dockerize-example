FROM node:16-alpine3.14
WORKDIR /app
COPY package*.json ./
RUN npm ci --quiet
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
