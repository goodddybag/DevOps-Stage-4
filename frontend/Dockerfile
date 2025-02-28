FROM node:12-slim

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies (only production dependencies for a leaner image)
RUN npm install

# Copy the rest of the application code
COPY . .

# Expose the application port
EXPOSE 8080

CMD ["npm", "start"]
