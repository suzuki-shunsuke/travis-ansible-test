# travis-ansible-test

Travis CI の実行環境を確認するためのリポジトリ

* https://docs.travis-ci.com/
* https://docs.travis-ci.com/user/ci-environment/

目標はAnsible Playbookのテストで失敗しないようにすること(適切な設定を確認すること)。

## テスト 1.0.0

成功

```
$ ansible-playbook -i inventory test.yml --connection=local --sudo
```

```
# inventory
localhost
```

```yaml
# test.yml
- hosts: localhost
  connection: local
```

## テスト 2

 --sudo オプション外しても成功

## テスト 3
 
 --connection=localオプションを外しても成功

## テスト 4

inventoryファイルをなくしてみても成功

## テスト 5

travis.ci と ローカルでのplaybookを統一出来ないか模索。
まずは hostsを localhostからdefaultにしてみる

