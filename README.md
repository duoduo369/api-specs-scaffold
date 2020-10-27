API specs scaffold
===
Swagger API 脚手架。

使用此脚手架可以迅速的编写swagger文档，无需关心非swagger语法外的东西。

使用
---

docker-compose up

访问 http://localhost:8091/


目录结构组织
---

* 所有的 swagger 文件放在 `swagger_files` 目录下
* 公共的 definitions 定义安放在 `swagger_files/_definitions.yaml` 文件中
* 文件名以 `response_type.service.yml` 命名，例如书籍返回是 `text/html` 类则使用 `page.book.yml` 命名,
  返回为 json 则使用 `api.book.yml` 命名
* 每个 swagger 文件有独立的 definitions 和 paths 定义，它们会覆盖公共的 definition 定义
* 所有 swagger 文件共享同一个版本号，定义于 `swagger_files/_metadata.yaml`(TODO: 此为移动端考虑，待定)

其他约定
---

* OpenAPI Specification 使用 3.xx 版本，默认3.0.3
* vscode 安装 `OpenAPI(Swagger) Editor 编辑swagger, todo: 考虑 [swagger-editor](https://github.com/swagger-api/swagger-editor) 支持


怎样编写 swagger
---
* 语法参见文档 [OpenAPI Specification 3.0.3](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.3.md)
* swagger_files 添加对应文件或在已有文件中修改
* 如果是新添加的yml, 在 `docker-compose.yml` 的 `volumes` 和 `environment -> URLS` 下添加对应路由


TODO:
---
* 添加test工具，例如gitlab hook验证语法是否正确的lint.
