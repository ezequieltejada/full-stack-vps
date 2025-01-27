# Use official Bun image
FROM oven/bun:1.0 AS build
WORKDIR /app
COPY backend/package.json backend/bun.lockb ./
RUN bun install
COPY backend/ .
RUN bun run build

# Use a minimal image for production
FROM oven/bun:1.0
WORKDIR /app
COPY --from=build /app/dist .
EXPOSE 3000
CMD ["bun", "start"]