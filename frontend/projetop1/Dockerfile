FROM node:20-alpine
ENV NEXT_TELEMETRY_DISABLED=1
WORKDIR /app
COPY package*.json ./
RUN npm ci --no-audit --fund=false
COPY . .
ENV NODE_ENV=development
ENV HOST=0.0.0.0
ENV PORT=3000
EXPOSE 3000
CMD ["sh","-c","npm run dev -- -H ${HOST} -p ${PORT:-3000}"]
