# 使用合适的基础镜像，这里选择了 Python 3.9 的 slim 版本
FROM python:3.9-slim

# 设置工作目录
WORKDIR /app

# 复制当前目录内容到工作目录
COPY . .

# 更新包索引并安装必要的软件包
RUN apt-get update -y && \
    apt-get install -y build-essential libpq-dev

# 升级pip、setuptools和wheel
RUN pip install --upgrade pip setuptools wheel

# 安装依赖
RUN pip install -r requirements.txt

# 暴露应用程序运行的端口
EXPOSE 5153

# 设置环境变量
ENV DB_USERNAME=myuser
ENV DB_PASSWORD=new_password
ENV DB_HOST=127.0.0.1
ENV DB_PORT=5433
ENV DB_NAME=mydatabase

# 运行应用程序
CMD ["python", "app.py"]

