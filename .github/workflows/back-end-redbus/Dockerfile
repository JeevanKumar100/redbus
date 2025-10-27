# Use official Node LTS
FROM node:18-alpine

# Create app directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json first to leverage cache
COPY package*.json ./

# Install dependencies
RUN npm ci --only=production

# Copy app source
COPY . .

# If you have environment variables in config.env, they should be provided at runtime (do not copy local config.env)
# Expose port (adjust if your app uses different port)
EXPOSE 5000

# Start command (use process manager or node directly)
# If your package.json has a start script, use it; otherwise adjust accordingly.
CMD ["npm", "start"]
