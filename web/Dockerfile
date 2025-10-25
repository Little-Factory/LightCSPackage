# Nginx 1.26 (stable) for ARM64
FROM nginx:1.26-alpine

# デフォルト設定を削除
RUN rm /etc/nginx/conf.d/default.conf

# カスタム設定をコピー
COPY default.conf /etc/nginx/conf.d/

# ポート公開
EXPOSE 80

# Nginxをフォアグラウンドで実行
CMD ["nginx", "-g", "daemon off;"]