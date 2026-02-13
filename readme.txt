ファイル名を日本語にしてしまっているので環境によってはコンパイルできないことがある．
その場合はファイル名のエンコードを一時的にeuc-jpに変更してから行えばよい．

linuxの場合：
$ apt-get install convmv
$ cp -r 係の引き継ぎ資料 tmp
$ cd tmp
$ convmv -f utf8 -t euc-jp * --notest
$ latexmk main
$ mv main.pdf ../
$ cd ..
$ rm -fr tmp

一応，一時ファイルを使ってコンパイルしているのでファイル名のエンコードを戻していない．
