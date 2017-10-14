# Unity調査メモ

## 調査予定事項
* Unity ログ出力
* Unity Windows デスクトップアプリケーションの作成・実行方法
* キーボードやマウス入力のハンドリング
* Unityコンテンツが動作するユーザーコントロールの作成（Windows Forms）
 * 3D
 * 2D
 
## チュートリアル 
Unity起動後、Learnタブのほうから、各種チュートリアル用のソース（完成版）が取得可能<br>
解説については、下記<br>
https://unity3d.com/jp/learn/tutorials
 
## .NET 4.6 対応
Unityのチュートリアルにあるサンプルソースは、.NET 3.5及びC#4<br>
これを、.NET 4.6 及び C#6 にするには、<br>
Edit -> Project Settings -> Player<br>
を選択し、<br>
右側ペインの、<br>
Other Settings -> Configuration -> Scripting Runtime Version<br>
を<br>
.NET 4.6<br>
に変更する。変更後、Unityエディタを再起動する。

UnityのC#プロジェクトファイル、ソリューションファイルは、自動生成されるので、<br>
元からあったものを削除し、Unityエディタからスクリプトファイルをダブルクリックして、<br>
Visual Studioを再度表示するようにすると、<br>
そのタイミングでC#6を使用するよう設定されたプロジェクトファイルが再度生成され、使用可能になる。<br>

## Unity ログ出力
UnityのConsoleに出力される。<br>
Consoleの表示：Ctrl + Shift + C （メニューからは、Windows -> Console）<br>
コード：Debug.Log、Debug.LogWarning および Debug.LogError

Input.GetAxisは、ブレークの条件で「0でない」を設定しても止まらず。<br>
ログ出力したところ、各軸ともに、-1～1の範囲で変化していることを確認。
