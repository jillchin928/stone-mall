


### 啟動 Docker 容器 在專案根目錄下執行以下指令來啟動 MySQL 容器：

docker-compose up -d
這會啟動 MySQL 容器並在背景運行。執行後，你可以透過以下指令檢查容器是否正常運行：

docker ps
若一切順利，你會看到 mysql_container 這個容器在運行。

docker-compose down

### 步驟 3：測試 MySQL 連線
當 MySQL 容器啟動後，Spring Boot 應該能夠自動連線到資料庫。如果你已經設置了 spring.jpa.hibernate.ddl-auto=update，那麼 Spring Boot 在啟動時會自動生成資料表。

你可以檢查 Spring Boot 日誌，看是否有成功連接 MySQL 資料庫：

2025-02-22 15:42:01.234  INFO 12345 --- [           main] o.hibernate.jpa.internal.util.LogHelper  : HHH000204: Processing PersistenceUnitInfo [name: default]
2025-02-22 15:42:01.243  INFO 12345 --- [           main] org.hibernate.dialect.Dialect            : HHH000400: Using dialect: org.hibernate.dialect.MySQL8Dialect
2025-02-22 15:42:01.259  INFO 12345 --- [           main] o.hibernate.hql.internal.ast.QueryTranslatorFactory  : HHH000397: Using ASTQueryTranslatorFactory
如果 Spring Boot 成功連接到 MySQL，則表示設定成功。