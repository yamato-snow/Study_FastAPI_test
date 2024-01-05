# fastAPI_test

## Python

### Python 環境構築

M1 mac の場合 必要に応じて実施

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
echo 'eval $(/opt/homebrew/bin/brew shellenv)' >> ~/.zprofile
source ~/.zprofile
brew update
brew install python
```

## fastAPI

### fastAPI 導入

```bash
pip install fastapi
pip install "uvicorn[standard]"
```

または

```bash
yarn
yarn setup
```

### サンプル

<a title="Gitpod" href="https://gitpod.io/#https://github.com/cti1650/fastAPI_test" target="_blank" class="btn btn-primary">Gitpodでサンプルを実行</a>

#### 本番リンク

|デプロイ先|URL|
|:-:|:-|
|deta|[https://ues2ls.deta.dev/](https://ues2ls.deta.dev/)|
|vercel|[https://fast-api-test.vercel.app/](https://fast-api-test.vercel.app/)|
|heroku|[https://fastapi-test-cti-tl.herokuapp.com/](https://fastapi-test-cti-tl.herokuapp.com/)
|Cloud Functions|[https://asia-northeast1-endless-set-138723.cloudfunctions.net/fastapi-test](https://asia-northeast1-endless-set-138723.cloudfunctions.net/fastapi-test)

```python
from typing import Optional

from fastapi import FastAPI

app = FastAPI()


@app.get("/")
def read_root():
    return {"Hello": "World"}


@app.get("/items/{item_id}")
def read_item(item_id: int, q: Optional[str] = None):
    return {"item_id": item_id, "q": q}
```

### サーバー立ち上げ

```
uvicorn main:app --reload
```

または

```
yarn serve
```

### requirements.txt 作成

```plane:requirements.txt
fastapi
```

### Deta 登録

[Deta Cloud](https://www.deta.sh/?ref=fastapi)

### Deta CLI インストール

```
curl -fsSL https://get.deta.dev/cli.sh | sh
```

### Deta 環境変数定義

```
echo 'export PATH=~/.deta/bin:$PATH' >> ~/.bash_profile && source ~/.bash_profile
```

### Deta 動作確認

```
deta --help
~/.deta/bin/deta --help
```

### Deta CLI Login (エラーになるため Chrome で実施要)

```
deta login
~/.deta/bin/deta login
```

### Deta 新規連携

```
deta new
~/.deta/bin/deta new
```

### Deta デプロイ

```
deta deploy
~/.deta/bin/deta deploy
```

## 参考にしたサイト

- [M1 Mac でできるだけ楽に Python 環境を構築する - Qiita](https://qiita.com/C2_now/items/c85be2ffeacd61cc7207)
- [tiangolo/fastapi: FastAPI framework, high performance, easy to learn, fast to code, ready for production](https://github.com/tiangolo/fastapi)
- [Deta にデプロイ - FastAPI](https://fastapi.tiangolo.com/ja/deployment/deta/)
- [Python Tutorial | Deta Docs](https://docs.deta.sh/docs/base/py_tutorial/?ref=fastapi)
- [DETA](https://web.deta.sh/home/cti1650/default/micros)
- [Python3.9 を Homebrew で M1 Mac にインストールする（2021 年 3 月 16 日時点） - ちゃぱブログ / エンジニアリング / マネジメント](https://as-chapa.hatenablog.com/entry/m1-python-install-20210316)
- [Python をローカルで利用できるようにする](https://zenn.dev/souq/articles/7d752c7a80c488cabd19)
- [brew でインストールに失敗する時の対処メモ](https://zenn.dev/souq/articles/3c0591a50f39269793c9)
- [Chrome ウェブストア - gitpod](https://chrome.google.com/webstore/search/gitpod?hl=ja)
- [Heroku deployment of Fastapi (Python) running on uvicorn: Web process failed to bind to $PORT - Stack Overflow](https://stackoverflow.com/questions/70608215/heroku-deployment-of-fastapi-python-running-on-uvicorn-web-process-failed-to)  
- [AWS LambdaとCloud FunctionsにFastAPIをデプロイする方法 - Enlone](https://lonesec.com/2020/09/12/deploy_to_functions_with_agraffe/)  
- [.gcloudignoreの書き方](https://zenn.dev/satohjohn/articles/11df180df878ac)  
