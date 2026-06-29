# morebounty 路径与参数字典

只在授权SRC范围内使用。命中后立刻转深挖，不继续无脑爆破；Payload只选低影响探针。

## 使用原则

- 每轮只选当前漏洞类相关的小字典，不全站喷。
- 手工低速验证；不使用高并发扫描器或全量脚本。
- Payload优先使用随机标记、测试对象、只读OOB和可回滚动作。
- 禁止破坏性写入、长延迟、资源消耗、批量导出、真实用户数据和真实业务动作。

## 首轮路径字典

只用高信号路径；命中后立刻转深挖，不继续无脑爆破。

```text
API/文档:
/api/ /api/v1/ /api/v2/ /rest/ /graphql /gql /openapi.json /swagger.json /api-docs /docs /.well-known/

认证/身份:
/login /register /signup /logout /password/reset /forgot /mfa /2fa /oauth/authorize /oauth/callback /sso /saml /jwt /jwks.json

管理/内部:
/admin /manager /console /dashboard /internal /ops /backoffice /cms /moderator /review /debug /status /health /metrics

配置/源码/备份:
/.env /.git/config /.svn/entries /config.json /config.yaml /credentials.json /backup.zip /backup.sql /dump.sql /build-info /actuator/env /actuator/heapdump

文件/导入导出:
/upload /uploads/ /import /export /download /download.php /download.jsp /download.do /down.php /readfile.php /file.php /file /files /preview /template /report /invoice /avatar /media /static/ /assets/

Java/Spring/Tomcat:
/WEB-INF/web.xml /WEB-INF/classes/application.properties /WEB-INF/classes/application.yml /META-INF/MANIFEST.MF /manager/html

业务高价值:
/order /cart /checkout /pay /payment /refund /wallet /coupon /points /subscription /invoice /tenant /org /invite

实时/异步:
/ws /websocket /socket.io /events /callback /webhook /notify /task /job /queue /render /pdf /screenshot
```

## 受限路径变体字典

遇到401/403/404伪装时，只对已命中的高价值路径做变体，不全站跑。

```text
基础:
/path/ /path/. /Path /PATH /path%20 /path%09 /path? /path.json /path.html /path/~

编码/规范化:
/%70ath /path%2f /path%252f /%2e/path /./path //path /path/./ /.//path

Java/Tomcat:
/path; /path;foo=bar /path;x /path..;/ /;/path /static/..;/WEB-INF/web.xml

Windows/IIS:
/path\\ /path\\..\\/ /path;.css /path::$DATA

组合:
///path/// /./path/./ /path/..;/path /%00/path /path%00 /path%00.json
```

## 首轮参数字典

按漏洞类选，不全量喷。

```text
对象/租户/越权:
id user_id uid account_id member_id tenant_id org_id company_id order_id invoice_id file_id project_id role isAdmin permission owner

文件/路径:
file filename filepath path page include template view load read download readfile dir folder root lang doc document content src inputFile hdfile XFileName FileUrl

URL/SSRF/跳转:
url uri target link href callback redirect redirect_uri next return returnUrl continue dest destination redir go forward out to rurl domain host image avatar webhook endpoint feed

查询/注入:
q query search keyword filter sort order by group limit offset where fields columns format callback

认证/token:
token access_token refresh_token code state nonce session sid jwt kid alg key email phone invite reset otp mfa

批量/隐藏字段:
ids items data metadata extra profile settings config debug admin verified tier plan price amount currency quantity status

缓存/静态后缀:
.css .js .jpg .png .gif .svg .ico .woff .woff2 .ttf .pdf .json
```
