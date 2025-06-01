# Use a specific Alpine version that addresses the Trivy vulnerabilities
FROM alpine:3.21.4

# Install security updates and dependencies
RUN apk update && apk upgrade && \
    apk add --no-cache \
    nginx \
    nodejs \
    npm

# Set working directory
WORKDIR /app

# Copy package files first for better caching
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy application files
COPY . .

# Build the application (include the OpenSSL fix)
ENV NODE_OPTIONS=--openssl-legacy-provider
RUN npm run build

# Configure nginx
COPY nginx.conf /etc/nginx/nginx.conf

# Expose port 80 (standard HTTP port for ingress)
EXPOSE 80

# Start nginx in foreground
CMD ["nginx", "-g", "daemon off;"]
