
# 用户积分
user_score

```
create table user_score(

user_name varchar(5) primary key not null,
score bigint default '0'

);
```
user_score_detail

```
create table user_score_detail(

user_name varchar(5) primary key not null,
score bigint default '0'

);
```

## 用户创作内容积分

用户每发布一篇文档加２０分（业务表）

用户每发布一篇课程加３０分（业务表）

用户每发布一篇博文加１０分（业务表）


用户每发布一篇问题加５分（业务表）

用户每发布一篇问题答案加５分（业务表）

用户论坛每发布一条帖子加５分（业务表）


## 用户主动行为积分

用户每登录一次加2分（日志表）

用户每发表一次评论加2分（业务表）

用户每点赞一次加2分（业务表）

用户每收藏一次加2分（业务表）

用户每关注一个用户加2分（业务表）


## 用户被动行为积分

用户每发表一次评论，评论主体所属用户 加2分（业务表）

用户每点赞， 点赞主体所属用户一次加2分（业务表）

用户每收藏，收藏主体所属用户 一次加2分（业务表）

用户每关注一个用户 ，被关注用户加2分（业务表）

<!--stackedit_data:
eyJkaXNjdXNzaW9ucyI6eyJPZHBXN1VXNHhMODkwZjBMIjp7In
N0YXJ0IjoyMCwiZW5kIjoxMjEsInRleHQiOiJgYGBcbmNyZWF0
ZSB0YWJsZSB1c2VyX3Njb3JlKFxuXG51c2VyX25hbWUgdmFyY2
hhcig1KSBwcmltYXJ5IGtleSBub3QgbnVsbCxcbnNjb3Jl4oCm
In0sIk1sSHA3MVg2Ykd3TXBCNGMiOnsic3RhcnQiOjE0NSwiZW
5kIjoyNTcsInRleHQiOiJgYGBcbmNyZWF0ZSB0YWJsZSB1c2Vy
X3Njb3JlX2RldGFpbChcblxudXNlcl9uYW1lIHZhcmNoYXIoNS
kgcHJpbWFyeSBrZXkgbm90IG51bGws4oCmIn19LCJjb21tZW50
cyI6eyI4VTI2MUk1cU9KbWJQREprIjp7ImRpc2N1c3Npb25JZC
I6Ik9kcFc3VVc0eEw4OTBmMEwiLCJzdWIiOiJnaDo0MDM3NTQ0
NSIsInRleHQiOiLnlKjmiLfnp6/liIbooagiLCJjcmVhdGVkIj
oxNjY4MzQ5MDUyNDc5fSwiVFVTSE9qZ21vTFJ0OFdGdSI6eyJk
aXNjdXNzaW9uSWQiOiJNbEhwNzFYNmJHd01wQjRjIiwic3ViIj
oiZ2g6NDAzNzU0NDUiLCJ0ZXh0Ijoi55So5oi356ev5YiG6K+m
57uG6KGoIiwiY3JlYXRlZCI6MTY2ODM0OTA3MjAyMH19LCJoaX
N0b3J5IjpbLTE5ODc0OTY1NjgsLTIwMTUxNzIxMTIsMTIwMDE2
ODY1OSwtMTQzMjM2Mjk3Nyw5MDczODYyMDMsMTMzODUwNzYzN1
19
-->