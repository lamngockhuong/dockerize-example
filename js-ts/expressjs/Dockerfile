FROM node:16-alpine3.14
WORKDIR /app
COPY . .
RUN npm ci --quiet
CMD ["npm", "start"]
