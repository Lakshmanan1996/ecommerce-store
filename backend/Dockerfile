# =========================================================
#  Node.js – Multi Stage (Production)
# =========================================================

# Build stage
FROM node:16 AS build

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

# Runtime stage
FROM node:16-alpine

WORKDIR /app
COPY --from=build /app ./

EXPOSE 5000

CMD ["node", "app.js"]
