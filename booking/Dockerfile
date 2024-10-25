# Use the official Node.js image as the base image
FROM node:18-alpine

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json (if available) to the working directory
COPY package*.json ./

# Install application dependencies
RUN npm install --production

# Copy the rest of the application files to the working directory
COPY . .

# Run Prisma generate to generate the client
RUN npx prisma generate

# Expose the port the app runs on
EXPOSE 3003

# Command to run the application
CMD ["npm", "start"]
