# Etapa 1: Construcción
FROM node:18-alpine AS builder

# Establecer directorio de trabajo
WORKDIR /app

# Copiar los archivos necesarios para instalar dependencias
COPY package*.json ./

# Instalar dependencias
RUN npm install

# Copiar el resto del código fuente
COPY . .

# Compilar TypeScript a JavaScript
RUN npm run build

# Etapa 2: Imagen final
FROM node:18-alpine

# Establecer directorio de trabajo
WORKDIR /app

# Copiar solo los archivos necesarios desde la etapa de construcción
COPY --from=builder /app/dist ./dist
COPY --from=builder /app/node_modules ./node_modules

# Exponer el puerto de la aplicación
EXPOSE 3000

# Comando por defecto para ejecutar la aplicación
CMD ["node", "dist/main.js"]
