FROM gitlab.praktikum-services.ru:5050/k.kudelich/momo-store/node:16-alpine as builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

FROM gitlab.praktikum-services.ru:5050/k.kudelich/momo-store/nginx:1.23.3-alpine
COPY --from=builder /app/dist /usr/share/nginx/html
EXPOSE 8080
