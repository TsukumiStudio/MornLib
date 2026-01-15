# MornLib

## 概要

基本的なユーティリティ、データ構造、デザインパターン実装の統合ライブラリ。

## 依存関係

| 種別 | 名前 |
|------|------|
| 外部パッケージ | VContainer, UniRx, UniTask |
| Mornライブラリ | なし |

## 使い方

### シングルトン

```csharp
public class MyClass : MornSingletonMono<MyClass>
{
    // 自動的にシングルトンとして機能
}

// アクセス
MyClass.I.DoSomething();
```

### ステートマシン

```csharp
var sm = new MornStateMachine<StateType>();
sm.ChangeState(StateType.Idle);
```

### オブジェクトプール

```csharp
var pool = new MornObjectPoolMono<Enemy>(prefab, parent, 10);
var enemy = pool.Rent();
pool.Return(enemy);
```

### その他のサブモジュール

- MornDictionary: 列挙型・オブジェクト辞書
- MornFPS: FPS計測
- MornSwordTrail: 剣跡エフェクト
- MornGridLayoutMono: グリッドレイアウト
- MornTcgLayoutMono: TCGカード風レイアウト
