FROM node:18-alpine AS build
WORKDIR /app

# First copy only package files for better caching
COPY package*.json ./
RUN npm install

# Then copy the rest
COPY . .
# Fix for Node.js OpenSSL issue
ENV NODE_OPTIONS=--openssl-legacy-provider
RUN npm run build

# Use specific nginx alpine version to reduce vulnerabilities
FROM nginx:1.25.3-alpine
COPY --from=build /app/build /usr/share/nginx/html

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
