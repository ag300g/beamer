## beamer
---

#### 用户手册
[beamer用户手册](http://www.docin.com/p-633733605.html)
#### 最基本代码
```
\documentclass{beamer}        %使用beamer文档类
\begin{document}              
\begin{frame}                 %frame：新建一个幻灯片
hello, world
\end{frame}
\end{document}
```
#### 我的PPT

```
\documentclass[xcolor=dvipsnames,CJK]{beamer}
%\usepackage[utf8]{inputenc} % this is needed for german umlauts
\usepackage[english]{babel} % this is needed for german umlauts
\usepackage[T1]{fontenc}    % this is needed for correct output
%\usecolortheme[named=gray]{structure} %改变主题背景的颜色  可以使用RGB颜色 [RGB={205,173,0}]

\usepackage{bm}   %%可以用\bm命令给公式里面的字体加粗,平时的字体加粗是\bf

\usetheme{Darmstadt}                           % of umlauts in pdf
\usepackage[english]{babel}
%\usepackage{helvet}
%\usefonttheme{serif}  % 字体. 个人偏好有轮廓的字体. 去掉这个设置编译, 就看到不同了.
\setbeamertemplate{navigation symbols}{}   %% 去掉页面下方默认的导航条.
\useoutertheme{shadow}
\usefonttheme[onlylarge]{structurebold}

%%以下这段是在左下角加页码
\setbeamercolor{footcolor}{fg=white,bg=white!30!blue} % 设置字体和背景颜色
\setbeamertemplate{footline}{%
  \leavevmode%
  \hbox{%
    \begin{beamercolorbox}[wd=.120\paperwidth,ht=2.3ex,dp=1ex,right]{footcolor}%
       \insertframenumber{} / \inserttotalframenumber\hspace*{5ex}
    \end{beamercolorbox}}%
  \vskip0pt%
}

\setbeamertemplate{headline}{}     %把顶栏去除

%\setbeamertemplate{outlines}[default]
%%来改变itemize和enumerate中的标记，默认为2D三角形可选项有ball，circle，retangle
%%\newenvironment{sequation}{\begin{equation}\small}{\end{equation}}  %%使公式字体变小


\title[{\color{red}F}unctional {\color{red}E}nrichment {\color{red}A}nalysis for {\color{red}G}ene {\color{red}S}et]{\vskip0mm{\huge   Functional Enrichment \\\vskip2mm Analysis for Gene Set }\vskip4mm}


\author[lyl1212@gmail.com]{\vskip10mm\large   \textbf{Yinliang Liu}}

\institute[AMSS]{\vskip-5mm {\color{red!70!black}\small \em lyl1212@gmail.com\\} \vspace{5mm} \color{blue!70!black}    \small Institute of Applied Mathematics, AMSS, \\Chinese Academy of Sciences}

\date { \vskip-2mm\color{yellow!70!black}   \small December 4, 2014}

\pgfdeclareimage[height=0.5cm]{zhangroup}{0zhangroup}
\logo{\pgfuseimage{zhangroup}{\vspace {-15pt}}}
\begin{document}

\frame{\titlepage}
%------------------------------------------------------------------------------------------------------------1


\begin{frame}
\frametitle{\vskip -4mm Outline\vspace{6pt} }
\tableofcontents[allsections]
\end{frame}

%------------------------------------------------------------------------------------------------------------2

\section[Background]{Background}

\begin{frame}
\frametitle{\vskip -4mm Outline\vspace{6pt} }
\tableofcontents[currentsection]
\end{frame}

%----------------------------------------------------------------------------------------------------------3

\begin{frame}{\vskip -4mm Background\vspace{6pt} }
%\subframetitle{}  %%可以指定副标题

{\large\bf\color{blue!70!black}Workflow:}
   \begin{columns}               %通过开始一个column来约束插入图片的位置
\column{150mm}                %150mm可以调节左右位置
     \vspace{-2mm}\pgfdeclareimage[height=7cm]{1}{01}  %-2mm可以调节上下位置
\pgfuseimage<0->{1}
   \end{columns}

\end{frame}

%--------------------------------------------------------------------------------------------------------4
\section[Model]{Model}   %在有底栏和顶栏的情况下[]里面的内容可以显示在顶栏上
\subsection[Model I]{Model I}

\begin{frame}
\frametitle{\vskip -4mm Outline\vspace{6pt} }
\tableofcontents[currentsection]
\end{frame}
%--------------------------------------------------------------------------------------------------------5
\begin{frame}{\vskip -4mm Model I\vspace{6pt} }


{\large\bf\color{blue!70!black}Network-based Functional Analysis for Gene Set}
 \begin{columns}
\column{90mm}
     \vspace{-2mm}\pgfdeclareimage[height=6.5cm]{2}{02}
\pgfuseimage<0->{2}  %0-的意思好像是第0页以后会出现
 \end{columns}

\end{frame}
%---------------------------------------------------------------------------------------------------------6

\begin{frame}[label=m1]{\vskip -4mm Model I\vspace{6pt} }   %%做一个标记以供跳转

\begin{equation}
\begin{aligned}
 L(C&|p_1,p_2,q,G) \\
&=|E_1| \log p_1 + |E_2| \log (1-p_1)  \\
&\quad+|E_3| \log p_2 + |E_4| \log (1-p_2)   \\
&\quad+|N_A| \log q + |N_I| \log(1-q) - \alpha|C|
\end{aligned}
\end{equation}

\vspace {2mm}
\begin{columns}
\begin{column}{60mm}
     \pgfdeclareimage[height=4cm]{2}{02}
\vspace{42mm}\pgfuseimage<0->{2}  %0-的意思好像是第0页以后会出现
   \end{column}
%\vspace{-30mm}
\begin{column}{60mm}                       %%并列两栏的宽度的和因该为120mm（60+60）
\vskip -40mm
{\footnotesize (i)\hspace{0.55cm}$N_A$: nodes of other active genes\\
(ii)\hspace{0.45cm}$N_I$: nodes of other inactive genes\\
(iii)\hspace{0.35cm}$E_1$: edges from active categories to active core genes\\
(iv)\hspace{0.4cm}$E_2$: edges from active categories to inactive core genes\\
(v)\hspace{0.5cm}$E_3$: edges from core genes to active peripheral genes\\
(vi)\hspace{0.4cm}$E_4$: edges from core genes to inactive peripheral genes}
\end{column}
\end{columns}
 \vspace{-38mm}\hyperlink{d}{\beamerbutton{return}}
\end{frame}
%-----------------------------------------------------------------------------------------------------------7

\begin{frame}[shrink=39]
\frametitle{\vskip -4mm Model I\vspace{6pt} }
\Large\textbf{Model I can be formulated into an integer quadratic programming:}\vspace{3mm}
%\begin{footnotesize}
\begin{equation}
\begin{aligned}
 \max   \quad & \sum_i \sum_j x_i \bm M_{ij} g_j \log p_1 + \sum_i \sum_j x_i \bm M_{ij} (1-g_j) \log(1-p_1) \\
                  & + \sum_i \sum_j y_i \bm N_{ij} (1-y_j) g_j \log p_2 + \sum_i \sum_j y_i \bm N_{ij} (1-y_j) (1-g_j) \log(1-p_2)\\
                  & + \sum_j (1-y_j)(1-z_j)g_j \log q +\sum_j (1-y_j)(1-z_j)(1-g_j) \log(1-q)\\
                  & -  \alpha \sum_i x_i \\[0.5cm]
\text{s.t.} \quad & y_j \leq \sum_i \bm M_{ij} x_i, \  j = 1,2,\cdots,N \\
                             & y_j \geq \bm M_{ij} x_i, \qquad i = 1,2,\cdots,M, \quad j = 1,2,\cdots,N \\
                             & z_j \leq \sum_i \bm N_{ij} y_i, \  j = 1,2,\cdots,N \\
                             & z_j \geq \bm N_{ij} y_i, \qquad i = 1,2,\cdots,M, \quad j = 1,2,\cdots,N \\
                             & x_i = \{0,1\}, \qquad i = 1,2,\cdots,M \\
                             & y_j = \{0,1\}, \qquad j = 1,2,\cdots,N \\
                             & z_j = \{0,1\}, \qquad j = 1,2,\cdots,N
\end{aligned}
\end{equation}
%\end{footnotesize}
\end{frame}
%-----------------------------------------------------------------------------------------------------------------8

\begin{frame}[label=el]{\vskip -4mm Model I\vspace{6pt} }

 \begin{columns}
\column{90mm}
     \vspace{-2mm}\pgfdeclareimage[height=6.5cm]{7}{07}
\pgfuseimage<0->{7}  %0-的意思好像是第0页以后会出现
 \end{columns}
\vspace{10mm}\hyperlink{m2}{\beamerbutton{return}}
\end{frame}
%----------------------------------------------------------------------------------------------------------------9
\subsection[Model II]{Model II}

\begin{frame}
\frametitle{\vskip -4mm Outline\vspace{6pt} }
\tableofcontents[currentsection]
\end{frame}
%------------------------------------------------------------------------------------------------------------------10

\begin{frame}{\vskip -4mm Model II \vspace{6pt} }

   \begin{columns}               %通过开始一个column来约束插入图片的位置
\column{110mm}                %150mm可以调节左右位置
     \vspace{-3mm}\pgfdeclareimage[height=6cm]{4}{04}  %-2mm可以调节上下位置
\pgfuseimage<0->{4}
   \end{columns}

\end{frame}
%------------------------------------------------------------------------------------------------------------------11
\begin{frame}{\vskip -4mm Model II \vspace{6pt} }

   \begin{columns}               %通过开始一个column来约束插入图片的位置
\column{110mm}                %150mm可以调节左右位置
     \vspace{-3mm}\pgfdeclareimage[height=6cm]{5}{05}  %-2mm可以调节上下位置
\pgfuseimage<0->{5}
   \end{columns}
\end{frame}
%-------------------------------------------------------------------------------------------------------------------12

\begin{frame}{\vskip -4mm Model II \vspace{6pt} }

   \begin{columns}               %通过开始一个column来约束插入图片的位置
\column{110mm}                %150mm可以调节左右位置
     \vspace{-3mm}\pgfdeclareimage[height=6cm]{6}{06}  %-2mm可以调节上下位置
\pgfuseimage<0->{6}
   \end{columns}

\end{frame}

%-------------------------------------------------------------------------------------------------------------------13


\begin{frame}{\vskip -4mm Model II \vspace{6pt} }

\begin{columns}               %通过开始一个column来约束插入图片的位置
   \begin{column}{40mm}                %150mm可以调节左右位置
     \vspace{-3mm}\pgfdeclareimage[height=6cm]{5}{05}  %-2mm可以调节上下位置
\pgfuseimage<0->{5}
   \end{column}

   \begin{column}{80mm}
\textbf{A candidate modol:}
\begin{equation}
\begin{aligned}
\min \quad &|T-t| \\
\text{s.t.} \quad & t\geq \alpha G
\end{aligned}
\end{equation}
Where $T$ denotes the amount of genes the combination term contained , $t$ denotes the size of the intersection of the 'interesting' gene list and combination term set, and $G$ denotes the size of the 'interesting' gene list. $\alpha$ is a parameter to control the degree of coverage.
\end{column}
\end{columns}
\end{frame}

%-------------------------------------------------------------------------------------------------------------------14


\begin{frame}[label=m2]{\vskip -4mm Model II \vspace{6pt} }

\vskip 1mm  \textbf{Model II can be formulated into an integer programming:}
\begin{scriptsize}
\begin{equation}
\begin{aligned}
 \max   \quad & \sum_j (1-g_j) y_j + \lambda \sum_i x_i \\[0.1cm]
\text{s.t.} \quad & y_j \leq \sum_i \bm M_{ij} x_i, \  j = 1,2,\cdots,N \\
                             & y_j \geq \bm M_{ij} x_i, \qquad i = 1,2,\cdots,M, \quad j = 1,2,\cdots,N \\
                             & \alpha \leq \sum_j g_j y_j \\
                             & x_i = \{0,1\}, \qquad i = 1,2,\cdots,M \\
                             & y_j = \{0,1\}, \qquad j = 1,2,\cdots,N  \\
\end{aligned}
\end{equation}
\end{scriptsize}

{\vspace{-20pt} \footnotesize \begin{itemize}
\item[$\color{red!70!black}\checkmark$] \color{blue!70!black}Expatiation
\begin{itemize}
\item[-] \scriptsize$x_i$, $y_j$, $g_j$ and  $ \bm M_{ij}$ are defined as before. \hyperlink{el}{\beamerbutton{legend}}
\item[-] \scriptsize$\lambda $ can be defined to be $1/(M+ 1)$ to make sure that for each $T$ and $t$, the size of optimal solution is minimum($M$ is the amount of all terms).
\end{itemize}
\item [$\color{red!70!black}\checkmark$] Execution
\begin{itemize}
\item[-] \scriptsize from $\alpha=1$.
\item[-] \scriptsize for every optimal $Y$, let $\alpha=\sum_j g_j y_j + 1$,  continnue.
\item[-] \scriptsize Untill $\alpha=G$($G$ is the size of the 'interesting' gene list.).
\end{itemize}
\end{itemize}
}
\hyperlink{d}{\beamerbutton{return}}\vspace{4pt}
\end{frame}

%-------------------------------------------------------------------------------------------------------------------15


\section[Discussion]{Discussion}

\begin{frame}
\frametitle{\vskip -4mm Outline\vspace{6pt} }
\tableofcontents[currentsection]
\end{frame}
%-------------------------------------------------------------------------------------------------------------------16


\begin{frame}[label=d]
\frametitle{\vskip -4mm Discussion\vspace{6pt} }
\begin{itemize}[<+->]    %%用[<+->]就可以把一张幻灯片按条目分成若干份以逐条显示条目

\item {\color{blue!70!black}\Large \textbf{Models}}\\
\vspace{4pt}Are there some advice to the models previously mentioned ? \vspace{4pt}\\
\hyperlink{m1}{\beamerbutton{Model I}}  \hyperlink{m2}{\beamerbutton{Model II}}\vspace{4pt}\\

\item {\color{blue!70!black}\Large \textbf{Algorithm}}\\
\vspace{4pt}Any fast algorithm can get approximate answer adequate for further using ?\vspace{4pt}

\item {\color{blue!70!black}\Large \textbf{Meaning}}\\
\vspace{4pt}Where to focus on for further analysis ?\vspace{4pt}

\end{itemize}

\end{frame}

%------------------------------------------------------------------------------------------------------------17
\frame{\begin{center}\Huge Thank you for attention!\\\vspace{25mm} \small Email: \color{red!70!black} \textit{ lyl1212@gmail.com}\end{center}}    %%%用这种方式生成的致谢页的页码正好是最后一页
\end{document}


\\iffalse
{\Large\begin{itemize}
\item[$\color{red!70!black}\checkmark$] Cascade schedules

\begin{itemize}\item[-]Externalities
\item[-]Related works and Model
\item[-]Adoption maximization
\item[-] Regret-proof schedules
\end{itemize}
\item Network pricing with negative externalities

\end{itemize}
}
\\fi

```


#### 一个比较有用的博客
> [Martin Thoma](http://martin-thoma.com/latex-beamer/)

#### 自带主题查询
1. [Beamer theme gallery](http://deic.uab.es/~iblanes/beamer_gallery/index_by_theme.html)
2. [所有主题和内置颜色与样式的矩阵排列](http://www.hartwork.org/beamer-theme-matrix/)
3. [分类查询](http://www.docin.com/p-364727492.html)

#### 一些细节记录
1. `\documentclass[xcolor=dvipsnames]{beamer}`
> 就是告訴 Beamer 我們準備使用 xcolor 這個套件以進入多彩的
Beamer (一般 LATEX 也可用 `\usepackage{xcolor}` 引入)。其中
的 dvipsnames 是告訴 Beamer 你要用的顏色名稱定義。你不一
定要用 dvipsnames 的定義, 也可以用 svgnames
2. `\setbeamertemplate{navigation symbols}{}`
> 可以去掉PPT底部的工具栏（向前向后的翻页操作）
3. `\useoutertheme{infolines}`
> 底部可以显示標題、作者 (以縮寫方式呈現), 並且顯示頁碼。
4. `\title[Gene Set Functional Enrichment]{\\${}$\\{\Large   \em  Gene Set Functional Enrichment}\vspace{10mm}}\par`
> 1.`\\${}$\\` 可以在内容内部的前面个后面加上空行,效果等同于\vskip 7mm，区别是`\\${}$\\`隔得距离无法精细调节。
 2.`\vspace{10mm}`也是在内容内部加空行的方式，效果等同于`\vskip 10mm`，但用在内容前面时有细微区别，可在把`\\${}$\\`分别换成`\vspace{10mm}`和`\vskip 10mm`体会差别。
5. `\title[{\color{red}F}unctional {\color{red}E}nrichment {\color{red}A}nalysis for {\color{red}G}ene {\color{red}S}et]{\vskip-1mm{\huge   Functional Enrichment\\\vskip1mm for Gene Set }\vskip4mm}`
> 
6. `\institute[AMSS]{\vskip-5mm {\color{red!70!black}\small \em lyl1212@gmail.com\par} \vspace{5mm} \color{blue!70!black}    \small Institute of Applied Mathematics, AMSS, \\Chinese Academy of Sciences}`
> 1.通过`\color{blue!70!black}`得到70%的蓝和30%的黑的混合体
2.通过`{\color{red!70!black}\small \em lyl1212@gmail.com\\}`使得`\em`仅对邮箱起作用，而不是全部的内容
3.通过`\vskip-5mm`来是精细调节位置，-5指比模板中的位置上移5mm
4.`\par`==`\\`

7. `\pgfdeclareimage[height=0.5cm]{zhangroup}{zhangroup}`
`\logo{\pgfuseimage{zhangroup}{\vspace {-15pt}}}` 
> 这两行命令用来在最后一行加logo
`{\vspace {-15pt}}`可以微调logo的位置
8. 用`\iffalse`和`\fi`来注释整段话
9. LaTeX中的字体大小
> 从小到大依次是：
\tiny
\scriptsize
\footnotesize
\small
\normalsize
\large
\Large
\LARGE
\huge
\Huge
