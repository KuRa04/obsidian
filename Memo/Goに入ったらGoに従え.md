[https://gihyo.jp/news/report/01/GoCon2014Autumn/0002](https://gihyo.jp/news/report/01/GoCon2014Autumn/0002)

## ✅ シンプルで学習しやすい文法

- 文法がコンパクトで読みやすく、C言語系の経験がなくても比較的すぐに習得可能。
- コードスタイルの強制（`gofmt`）により、読みやすいコードが保たれる。

## 🚀 高速な実行性能

- 静的型付け・コンパイル型言語のため、実行速度が速い。
- C/C++に近いパフォーマンスを出しつつ、より安全な設計。

## ⚙️ 並行処理（Goroutine）が簡単

- `goroutine`と`channel`を使った並行処理が簡潔に記述可能。
- スレッドより軽量で、数万単位の並行処理も問題なし。

## 📦 豊富な標準ライブラリ

- HTTPサーバー、JSON処理、暗号化、テストなど、実用的な標準ライブラリが充実。
- 外部ライブラリに頼らずに、すぐにプロダクションレベルの開発が可能。

## 🧪 組み込みのテスト機能

- `go test`でユニットテストやベンチマークテストが簡単に実行できる。
- テストの書き方も直感的でシンプル。

## 🛠️ クロスコンパイルが容易

- 1つのマシンでWindows/Linux/macOS用のバイナリを生成可能。
- コンパイルされたバイナリは単一ファイルで、依存関係不要。

## 👥 コミュニティとエコシステム

- DockerやKubernetesなどのクラウドネイティブツールがGoで書かれており、業界でも注目度が高い。
- OSSの開発環境としても強力な基盤がある。

## 📚 静的型付けと安全性

- 静的型付けによる型チェックでバグを事前に防ぎやすい。
- nilポインタや型エラーを明示的に扱える設計。

### GoのInstall

```go
brew install go
```

### APIサーバ実装

```go
package main

import (
    "fmt"
    "net/http"
)

func helloHandler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintln(w, "Hello, World")
}

func main() {
    http.HandleFunc("/", helloHandler)
    fmt.Println("Server is running on <http://localhost:8080>")
    http.ListenAndServe(":8080", nil)
}

```

### コンパイル

```go
go run main.go
```

### curl

```go
curl <http://localhost:8080/>
```

### JavaとGoの違い

| 特徴              | Java                       | Go（Golang）                   |
| --------------- | -------------------------- | ---------------------------- |
| **開発元**         | Oracle（元はSun Microsystems） | Google                       |
| **登場年**         | 1995年                      | 2009年                        |
| **実行方式**        | JVM上でバイトコード実行（仮想マシン型）      | ネイティブバイナリにコンパイル（静的コンパイル）     |
| **言語のタイプ**      | オブジェクト指向                   | 手続き型 + 一部のOOP機能              |
| **構文の複雑さ**      | やや複雑（冗長）                   | シンプルで読みやすい                   |
| **並行処理**        | スレッドベース + Executor         | 軽量なGoroutine + Channel       |
| **パフォーマンス**     | 高速（ただしJVM起動オーバーヘッドあり）      | 非常に高速（ネイティブバイナリ）             |
| **メモリ管理**       | 自動GC                       | 自動GC                         |
| **ビルド/配布のしやすさ** | JVM必要（Jar, Warなど）          | 単一バイナリを生成し、そのまま配布可能          |
| **例外処理**        | try-catch構文あり              | 原則として明示的なエラーハンドリング（多用）       |
| **エコシステム**      | 豊富で成熟（Springなど）            | 急成長中（KubernetesなどがGo製）       |
| **クロスコンパイル**    | 標準では困難                     | 組み込みで簡単に可能（`GOOS`, `GOARCH`） |
| **学習コスト**       | 中〜高（特にOOPやJVM知識）           | 低め（構文がシンプル）                  |