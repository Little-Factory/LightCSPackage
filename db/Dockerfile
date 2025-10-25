# PostgreSQL 16 (stable) for ARM64
FROM postgres:16-alpine

# Alpine LinuxはARMに最適化されており軽量
# 追加設定が必要な場合はここに記述

# PostgreSQL設定の最適化（オプション）
RUN echo "shared_buffers = 256MB" >> /usr/local/share/postgresql/postgresql.conf.sample && \
    echo "max_connections = 100" >> /usr/local/share/postgresql/postgresql.conf.sample

EXPOSE 5432