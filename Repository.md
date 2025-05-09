# Amnesiac ML – Forgetting Specific Data in Neural Networks

本リポジトリは、論文 **“Amnesiac Machine Learning: Towards Machine Unlearning of Forgotten Entities”**  
（AAAI‑21）で提案された 2 つの手法

| 手法                | アイデアの概要 | 想定ユースケース |
|--------------------|---------------|------------------|
| **Unlearning**     | 対象クラスのサンプルにランダムな誤ラベルを与えて数エポックだけ追学習し、モデルを“混乱”させて忘れさせる | 対象データが比較的多いとき／実装が簡単 |
| **Amnesiac Unlearning** | 学習中に各ミニバッチの重み更新 Δθ を記録し、削除要求が来たら該当バッチ分だけ重みを巻き戻す | **対象データがごく少量**で即時削除したいとき |

を **PyTorch＋Jupyter Notebook** で再現・評価するコード一式です。  
論文 PDF も同梱されています。

---

## 収録ノートブック一覧

| ファイル名 | 目的 |
|------------|------|
| `Amnesiac_Unlearning‑MNIST.ipynb` | Δθ ロギングと巻き戻しの最小例（MNIST） |
| `Unlearning_Tester‑CIFAR100.ipynb` | 誤ラベル学習(既存手法)による Unlearning を CIFAR‑100/ResNet‑18 で検証 |
| `Amnesiac_ML_Evaluation.ipynb` | Amnesiac 手法を削除比率 0.1‑50 % でスケール評価 |
| `Model_Inversion_Attacks.ipynb` | 汎用モデル反転攻撃のベース実装 |
| `Unlearning_Model_Inversion‑resnet18.ipynb` | Unlearning/Amnesiac 後モデルで反転攻撃を比較 |
| `Membership_Inference_Attack.ipynb` | Shadow model によるメンバーシップ推論攻撃と忘却効果の比較 |


---

## セットアップ

1. python / jupyterの拡張機能をインストール
2. 仮想環境作成
3. command+shift+pでコマンドパレット表示、python:select interpreterから仮想環境を選択
4. 同様にコマンドパレットからJupyter: Select Interpreter to Start Jupyter Serverで仮想環境を選択

参考: https://qiita.com/ryu_pro1000/items/a31c3df951b1be0641db
