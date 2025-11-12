# ----- BUILD STAGE (optional if you have build steps) -----
# Use a node image to install deps
FROM node:20-alpine AS deps
WORKDIR /app
COPY package.json package-lock.json* ./
RUN npm ci --production

# ----- RUN STAGE -----
FROM node:20-alpine
WORKDIR /app

# Copy production node_modules from build stage
COPY --from=deps /app/node_modules ./node_modules

# Copy application source
COPY . .

# Environment
ENV NODE_ENV=production
ENV PORT=5000

EXPOSE 5000

# Start the app
CMD ["node", "server.js"]
