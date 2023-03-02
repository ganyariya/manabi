FROM node:19-alpine
WORKDIR /app
COPY . .
RUN npm install && npm run build

# build 時に --build-arg=2000 とすることで変更できる && Dockerfile の中だけの変数
ARG PORT=3000
# コンテナ時にも引き継がれる変数
ENV PORT=$PORT
# 明示化のためだけであり 実際に port 3000 を開くわけではない (別途 -p 3000:3000 でポートを開く必要がある)
EXPOSE $PORT

ENTRYPOINT ["npm", "run", "dev"]
