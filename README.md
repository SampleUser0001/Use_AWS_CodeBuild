# Use_AWS_CodeBuild
AWS CodeBuildを使ってみる。

## コマンド

``` sh
zip MessageUtil.zip ./*
aws s3 cp ./MessageUtil.zip s3://codebuild-${region-ID}-${account-ID}-input-bucket
```

### S3バケットを作成する

```sh
aws s3 mb s3://${bucket-name}
```

### アカウントIDを確認する

```sh
aws sts get-caller-identity
```

## 参考

- [CodeBuild の開始方法:AWSドキュメント](https://docs.aws.amazon.com/ja_jp/codebuild/latest/userguide/getting-started-overview.html)
  - 「このチュートリアルを完了するために AWS ルートアカウントは使用しないでください。」って書いてあるけどなんの権限がいるのよ・・・
- [AWS CLI での高レベル (S3) コマンドの使用:AWSドキュメント](https://docs.aws.amazon.com/ja_jp/cli/latest/userguide/cli-services-s3-commands.html#using-s3-commands-managing-buckets-creating)
  - S3バケットの作成
- [【小ネタ】AWS CLIでAWS Account IDが取れるようになりました！：DeveopersID](https://dev.classmethod.jp/articles/get-aws-account-id-with-get-caller-identity/)
  - アカウントIDの確認