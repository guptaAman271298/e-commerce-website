# Build React app
FROM node:18 AS build

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

# Accept build argument
# ARG VITE_PRODUCT_API
# Set it as environment variable for the build
ENV VITE_PRODUCT_API=${secrets.VITE_PRODUCT_API}

RUN npm run build

# Serve using NGINX
FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
