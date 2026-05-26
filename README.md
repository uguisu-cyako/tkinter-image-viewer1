# tkinter-image-viewer1
Python の Tkinter GUI と Pillow を使って画像を表示する簡単なデスクトップアプリ
## 使用技術
- Python 3.14
- Tkinter
- Pillow（PIL）
  
## 機能
- ボタンを押すと画像を表示
- Tkinter を使った簡単な GUI
  
## スクリーンショット
<img width="1485" height="1021" alt="image" src="https://github.com/user-attachments/assets/6889d8d3-2b51-4afa-8a08-b12b90f339b7" />
※ ボタンを押すと画像が表示される画面

## コード例
import tkinter as tk
import tkinter.filedialog as fd
import PIL.Image
import PIL.ImageTk

def dispPhoto(path):
    newImage = PIL.Image.open(path).resize((300,300))
    imageData = PIL.ImageTk.PhotoImage(newImage)
    imageLabel.configure(image=imageData)
    imageLabel.image = imageData

def openFile():
    fpath = fd.askopenfilename()
    if fpath:
        dispPhoto(fpath)

root = tk.Tk()
root.geometry("400x350")  

btn = tk.Button(text="画像を開く", command=openFile)
imageLabel = tk.Label()

btn.pack()
imageLabel.pack()

root.mainloop()


## 学んだこと・工夫した点
- Python の複数バージョン問題を解決し、正しい python.exe を指定して実行できるようにした
- Pillow が認識されないエラーを pip で解決
- Tkinter の geometry 指定で全角文字が原因のエラーを発見し修正
- コマンドプロンプトから実行してエラー内容を読む方法を習得
- GUI アプリの基本構造（root、Label、Button、pack）を理解した
  
## 今後の改善案
- 複数画像の切り替え機能
- 画像の拡大縮小
- ファイル選択ダイアログの追加
- UI デザインの改善


