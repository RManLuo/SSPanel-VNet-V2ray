# SSPanel-VNet-V2ray
基于[VNet-V2ray](https://github.com/ProxyPanel/VNet-V2ray)修改，对接SSPanel的V2ray后端。目前支持获取节点，用户信息，节点限速，暂不支持中转和审计规则。

此项目只是试验性质，不再更新，请关注[XrayR](https://github.com/XrayR-project/XrayR)
# 编译
1. [Go语言](https://golang.org/), [Bazel](https://docs.bazel.build/)
2. 依次运行
```sh
git clone https://github.com/RManLuo/SSPanel-VNet-V2ray.git SSPanel-VNet-V2ray && cd SSPanel-VNet-V2ray
go mod tidy
bazel build --action_env=PATH=$PATH --action_env=SPWD=$PWD --action_env=GOPATH=$(go env GOPATH) --action_env=GOCACHE=$(go env GOCACHE) --spawn_strategy local //release_vnet:v2ray_linux_amd64_package
```
3. 获得 `bazel-bin/release_vnet/v2ray-linux-64.zip`

# 使用
1. 生成配置文件config.json
```bash
cat config.json
{
  "api_server":"http://127.0.0.1:667", # Panel URL
  "key": "NimaQu", # webapi key
  "node_id":41 # Node id
}
```
2. 运行 
```
./vnet -config config.json
```

# License
 GNU GENERAL PUBLIC LICENSE
