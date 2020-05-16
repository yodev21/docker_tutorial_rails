# イメージ名にRuby(Ver2.6.5)の実行環境のイメージを指定
FROM ruby:2.6.5

# パッケージのリストを更新しrailsの環境構築に必要なパッケージをインストール
RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs

# プロジェクト用のディレクトリを作成
RUN mkdir /myapp

# ワーキングディレクトリに設定
WORKDIR /myapp

# プロジェクトのディレクトリにコピー
COPY Gemfile /myapp/Gemfile
COPY Gemfile.lock /myapp/Gemfile.lock

# bundle install実行
RUN docker-compose build --no-cache

# ビルドコンテキストの内容を全てmyappにコピー
COPY . /myapp