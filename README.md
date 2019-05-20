# api
STARMINEのAPIドキュメントを管理するリポジトリ  
https://sbiv-starmine.github.io/api/  

## Swagger
APIドキュメントの編集および閲覧にはSwaggerを利用し、`api.yaml`にまとめる  
Swaggerのバージョンには[OpenAPI 3.0.2](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md)を利用する  

### Swaggerのツール群について
- swagger-editor: `api.yaml`ファイルを編集
- swagger-ui:`api.yaml`ファイルを表示
- swagger-api:`api.yaml`ファイルのAPIをホスト

### docker-compose
上記のツール群をDockerコンテナでローカルにデプロイします  
事前に[docker-compose](http://docs.docker.jp/compose/install.html)をインストールしてください  

``` shell
#起動
docker-compose up -d

#確認
docker-compose ps
     Name                   Command               State               Ports
----------------------------------------------------------------------------------------
swagger-api      /usr/local/bin/apisprout / ...   Up      0.0.0.0:8083->8000/tcp
swagger-editor   sh /usr/share/nginx/docker ...   Up      0.0.0.0:8081->8080/tcp
swagger-ui       sh /usr/share/nginx/run.sh       Up      80/tcp, 0.0.0.0:8082->8080/tcp
```

- swagger-editor: http://localhost:8081
- swagger-ui:http://localhost:8082
- swagger-api:http://localhost:8083

## Github pages
本リポジトリは一旦Github Pagesを利用し、Swagger UIをホストする。  
ただし、認証がなくパブリックに公開してしまうのでホストの方法は要検討。  


