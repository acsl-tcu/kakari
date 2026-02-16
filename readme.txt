ファ\section*{係の引継ぎ資料について}

本リポジトリは，係の引継ぎ資料を \LaTeX{} で管理し，PDFとして一括生成するためのものである．
本フォーマットは，2025年度より GitHub 上で管理できるように整備された．

\section*{ファイル名が日本語の場合の注意点}

本資料では，ファイル名に日本語を使用している．
そのため，環境によっては \LaTeX{} のコンパイル時に文字コードの問題が発生し，
正常にコンパイルできない場合がある．

その場合は，ファイル名のエンコードを一時的に euc-jp に変換してから
コンパイルを行うことで回避できる．

以下に，Linux 環境での手順例を示す．

\subsection*{Linuxでのコンパイル手順（回避策）}

\begin{verbatim}
$ apt-get install convmv
$ cp -r 係の引き継ぎ資料 tmp
$ cd tmp
$ convmv -f utf8 -t euc-jp * --notest
$ latexmk main
$ mv main.pdf ../
$ cd ..
$ rm -fr tmp
\end{verbatim}

本手順では，一時ディレクトリを用いてコンパイルを行っている．
そのため，元のファイル名のエンコードを戻す必要はなく，
元データには一切変更を加えない構成となっている．

\section*{ブランチ構成について}

本リポジトリでは，年度ごとにブランチを分けて管理する．

\begin{itemize}
  \item \textbf{2024old-version} \\
  2024年度以前の係引継ぎ資料をまとめたブランチである．
  過去資料の参照用として保持している．
\end{itemize}

\section*{係の引継ぎ用 共通ルール（2025年度以降）}

2025年度以降は，以下のルールに従って資料を管理すること．

\begin{itemize}
  \item 各年度ごとに \texttt{20××nendo} という名前のブランチを作成する．
  \item 当該年度の係引継ぎ資料は，そのブランチ内にまとめる．
  \item 各係ごとの \LaTeX{} ファイルは \texttt{kakari/works} 以下に配置する．
  \item \texttt{main.tex} を実行することで，
        \texttt{kakari/works} 内にある各係の TeX ファイルが統合され，
        1つのPDFとして出力される．
\end{itemize}

\section*{補足}

\begin{itemize}
  \item 過去年度の資料は，原則として編集せず，参照用として保持する．
  \item 新年度の資料は，必ず新しい年度ブランチを作成して管理すること．
\end{itemize}
