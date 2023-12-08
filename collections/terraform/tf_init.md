---
  date    : 2023-12-08
  title   : 🆔 Terraform
  excerpt : XXXX
  tags    : ["🆔", "Terraform", "infrastructure"]
---

## || Terraform

`cf.` TerraformとProviderのリポジトリ及びdoc

|項目|分類|リポジトリ|doc|備考|
|:-|:-|:-|:-|:-|
|Terraform|本体
|[hashicorp/terraform](https://developer.hashicorp.com/terraform/docs)
|[Documentation | Terraform | HashiCorp Developer](https://github.com/hashicorp/terraform)
|hashicorp社のインフラ構築ツール。(oss)|
|Google Cloud
|Provider
|[hashicorp/terraform-provider-google](https://github.com/hashicorp/terraform-provider-google)
|[Google Cloud Platform Provider](https://registry.terraform.io/providers/hashicorp/google/latest/docs)
|Terraformでgcpを管理plugin|
|Looker
|Provider
|[hirosassa/terraform-provider-looker](https://github.com/hirosassa/terraform-provider-looker)
|[Looker Provider](https://registry.terraform.io/providers/hirosassa/looker/latest/docs)
|Terraformでlookerを管理plugin|
|AWS
|Provider
|[hashicorp/terraform-provider-aws](https://github.com/hashicorp/terraform-provider-aws)
|[AWS Provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
|Terraformでawsを管理plugin|

## || 導入

いずれかをインんストール
```shell
# terraformの場合
brew install terraform

# tfenvの場合
brew install tfenv
```

## || REFERENCE
- [【初学者向け】Terraformの基本](https://qiita.com/yutaroud/items/75915228d787f7b41fed) - Qiita
- [イチから学べるTerraform～基礎から実践を紹介するウェビナー動画を無料公開～](https://www.lac.co.jp/lacwatch/service/20230329_003331.html) - LAC WATCH
