# Unity調査メモ

## 調査予定事項
* Unity ログ出力
* Unity Windows デスクトップアプリケーションの作成・実行方法
* キーボードやマウス入力のハンドリング
* Unityコンテンツが動作するユーザーコントロールの作成（Windows Forms）
 * 3D
 * 2D
 
## チュートリアル 
Unity起動後、Learnタブのほうから、各種チュートリアル用のソース（完成版）が取得可能  
解説については、下記  
https://unity3d.com/jp/learn/tutorials
 
## .NET 4.6 対応
Unityのチュートリアルにあるサンプルソースは、.NET 3.5及びC#4  
これを、.NET 4.6 及び C#6 にするには、  
Edit -> Project Settings -> Player  
を選択し、  
右側ペインの、  
Other Settings -> Configuration -> Scripting Runtime Version<br>
を  
.NET 4.6  
に変更する。変更後、Unityエディタを再起動する。

UnityのC#プロジェクトファイル、ソリューションファイルは、自動生成されるので、  
元からあったものを削除し、Unityエディタからスクリプトファイルをダブルクリックして、  
Visual Studioを再度表示するようにすると、  
そのタイミングでC#6を使用するよう設定されたプロジェクトファイルが再度生成され、使用可能になる。  

## Unity ログ出力
https://docs.unity3d.com/jp/540/Manual/Console.html<br>

UnityのConsoleに出力される。<br>
Consoleの表示：Ctrl + Shift + C （メニューからは、Windows -> Console）  
コード：Debug.Log、Debug.LogWarning および Debug.LogError

Input.GetAxisは、ブレークの条件で「0でない」を設定しても止まらず。  
ログ出力したところ、各軸ともに、-1～1の範囲で変化していることを確認。

## Unity Windows デスクトップアプリケーションの作成・実行方法
File -> Build Settings -> Build  
プラットフォームを選択して作成できる。

## Unityコンテンツが動作するユーザーコントロールの作成（Windows Forms）
Unityコンテンツ側をdllにして使用するよりも、  
Unityコンテンツのプロセスから、自作のツールライブラリを呼び出して使用するほうがスムーズにいくようにみえる。  

Unityで作ったアプリを起動する際、解像度の指定を求められることから、  
一般的なWindowsアプリで行われる、画面のリサイズはあまり想定していないように思える。  

## UI System
https://unity3d.com/jp/learn/tutorials/topics/user-interface-ui <br>

Windows Forms などに連携する方法もあるようだが、  
基本はUnityのUIシステムを使用するのが好ましいと思われる。  

OnGUIというメソッドを定義してのハンドリングもある。  
https://qiita.com/hibiki8229/items/5bd675073c7e041e222f <br>



