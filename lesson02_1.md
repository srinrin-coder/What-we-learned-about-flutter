# Lesson2-1: FlutterのWidget構造

## Flutterのウィジェットの構造と仕組み

Flutterでは、すべてのUI要素がウィジェット（Widget）として構築される。アプリの開始点である`main`関数から、UIの構築が始まる。

### main関数とrunApp

- アプリのエントリーポイントは`main()`関数。
- `runApp()`関数を使って、アプリのUIとなるウィジェットのインスタンスを起動する。

### StatelessWidgetの継承

- `runApp()`の引数には、`StatelessWidget`を継承したクラスのインスタンスを渡す。
- このクラスがアプリ全体のUIの起点となる。

### buildメソッドとMaterialApp

- `StatelessWidget`を継承したクラスには、UIを返すための`build(BuildContext context)`メソッドを定義する。
- `build()`の戻り値には`MaterialApp`ウィジェットを返す。
- `MaterialApp`の`home`引数に、アプリ内に表示する具体的なウィジェット（例：`Scaffold`）を設定する。

## Scaffoldとは？

- `Scaffold`は、Flutterアプリにおける基本的なレイアウト構造を提供するウィジェット。
- アプリバー（`AppBar`）、ボディ（`body`）、ドロワー（`Drawer`）などの構成要素を含む。
- ユーザーがよく目にする画面の土台部分に相当する。

---

## 授業で書いたコード

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      home: Scaffold(
        appBar: AppBar(
          backgroundColor: Colors.blue,
          title: Text('Hello, Flutter'),
        ),
        body: Text('Hello, Flutter World!', style: TextStyle(fontSize: 32.0)),
      ),
    );
  }
}
