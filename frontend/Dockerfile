FROM node:18-alpine AS build

WORKDIR /app

# Copy package files first
COPY package.json package-lock.json ./

RUN npm install --frozen-lockfile

# Copy rest of the app files
COPY . .

# Build the app
RUN npm run build

# Serve the app with Nginx
FROM nginx:alpine

# Copy build output (not dist) to Nginx
COPY --from=build /app/build /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
