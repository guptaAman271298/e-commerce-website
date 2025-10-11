# Use Node.js base image
FROM node:18

# Set working directory
WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install --production

# Copy rest of the code
COPY . .

# Expose backend port
EXPOSE 8000

# Start the server
CMD ["npm", "run", "dev"]
