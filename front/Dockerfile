# Node.js 20 LTS (stable) for ARM64
FROM node:20-alpine

# 作業ディレクトリ設定
WORKDIR /app

# 環境変数設定
ENV NODE_ENV=development \
    PATH=/app/node_modules/.bin:$PATH

# package.jsonとpackage-lock.jsonをコピー
COPY package*.json ./

# 依存パッケージのインストール
RUN npm ci --silent && \
    npm cache clean --force

# アプリケーションコードをコピー
COPY . .

# ポート公開
EXPOSE 3000

# 開発サーバー起動
CMD ["npm", "start"]