# component-4d-labels
ラベルエディターの修正版

### インストールする場所

Mac（アプリケーションパッケージ内）

```
Contents/Resources/Internal User Components/4D Labels.4dbase
```

Windows（アプリケーションフォルダー）

```
./Resources/Internal User Components/4D Labels.4dbase
```

#### ACI0099200

問題：フォームを使用し，用紙設定を``Orientation option (2)``（横向き）に設定した場合，ラベルが正しく配置されません。

誤

[label.pdf](https://github.com/4D-JP/component-4d-labels/files/3189711/label.pdf)

正

[label.pdf](https://github.com/4D-JP/component-4d-labels/files/3189709/label.pdf)

修正する箇所

#### メソッド：``Print_Label`` 行：``120``-``130``

```
//If ($Lon_orientation=2)  // Landscape

//$Lon_columns:=$Lon_width\$Lon_labelHeight
//$Lon_rows:=$Lon_height\$Lon_labelWidth

//Else 

$Lon_columns:=$Lon_width\$Lon_labelWidth
$Lon_rows:=$Lon_height\$Lon_labelHeight

//End if 
```
