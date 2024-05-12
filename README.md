# Mei's Git Tutorial

# Why?

Have you ever written something, edited it, and realized that the old version was better? 

Thankfully the "undo" button exists, but it isn't perfect.  You might have shut off the computer and turned it on; no undo function would be available.

Microsoft Word has a "Version History" feature that lets you view and load older versions of your saved document.  This is even better.  

However, what if you are experimenting and want to try different ideas out?  You can try things like having multiple files, but this gets hard to manage.  

This gets much worse when you try to write something with a friend.[1] You might decide to take the story in one direction, while your friend chooses another. How are you going to merge these two versions of the story together?  

In the IT world, we use a program called "git" to handle problems like this.  

Git is a "Version Control System" and is used to help people keep track of changes to a system.  It can help you see old version of your document, and allow you to try out new things on different versions without modifying your main version (the "Master branch") of your work.

You can use Linux on nearly any system available today; Windows, MacOS, Linux, and BSD all have versions that you can use.  

Our job is going to be learn git - today.


# なぜ？

何かを書いて、編集して、古いバージョンの方が良かったと気づいたことはありますか？

幸いにも「元に戻す」ボタンがありますが、完璧ではありません。コンピュータをシャットダウンして再起動した場合、その「元に戻す」機能が使えないかもしれません。

まだ諦めちゃだめ。Microsoft Wordを使っているなら「バージョン履歴」という機能があり、保存された文書の古いバージョンを表示して読み込むことができます。うえぃ、元に戻されました！

しかし、もし実験的に異なるアイデアを試したい場合はどうでしょうか？複数のファイルを使ってみる方法がありますが、そうすれば管理が難しくなる。

友人と何かを書くとき、さらに問題は悪化します。[1] あなたは物語を一方向に進めるかもしれませんが、友人は別の方向を選ぶかもしれません。これら二つのバージョンの物語をどうやって一つに統合しますか？

職場では、このような問題を解決するために「git」というプログラムを使用します。

Gitはバージョン管理システムの一つで、システムに加えられた変更を追跡するのに役立ちます。このシステムを使うと、文書の古いバージョンを確認したり、メインバージョン（マスターブランチと呼ばれる）を変更せずに新しいアイデアを異なるバージョンで試すことができます。

gitはWindows、MacOS、Linux、BSDに対応したバージョンがあるから、君はすぐ対応できます。

これでgitが何かがわかったので、次はその使い方を学びましょう。


[1] Communicating with a lot of people is a very hard problem.  There is an unrelated classic book about this called "The Mythical Man-Month" that was written in 1975.  While it does not deal directly with version control, you might find it helpful to read when you decide to manage projects.


# Install git NOW

I assume you are on Windows.  This will require some extra work to use for work, but it's fine for when you are starting out.  One day you may decide to graduate to a Linux system which will – ironically – make the process easier.

Microsoft offers a step-by-step tutorial to [install Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/install).  This is a must.  WSL2 is used by nearly everyone; only highly experienced grey beards (experienced older developers) and developers with very specific circumstances do not use WSL2.

Next you are going to have to install your development environment tools.  Again, Microsoft [has a tutorial for you](https://learn.microsoft.com/en-us/windows/wsl/setup/environment).  This will install Ubuntu which is fine.  Ignore the part about other distributions for now.

A few notes about the instructions:

	- It is also going to ask you to install a "code editor"; for the time being, use the free Visual Studio Code.  In the future, you are going to learn about the many options you have [2].  
	- Docker is also mentioned; install it. It’s not immediately necessary, but it will be beneficial later.
	- You don't have to worry about databases yet, or about GPU acceleration.  
	- You should learn the WSL commmands, but we will discuss those later.

Finally, you can install Git using the [tutorial here](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-git).  You can ignore anything that suggests you make a Github account; Microsoft owns Github now (so of course they would tell you to get an account).  You also can ignore the part about Git Credential Manager, it has nothing to do with your work for now.


# gitをインストールせよ！


Windowsを使用していると思います。仕事に使用する際に少し手間がかかりますが、初心者として大丈夫です。　いつかWindowsを卒業し、MacやLinuxを利用するとプロセスがより簡単になります。

MicrosoftはWindows Subsystem for Linux（WSL）をインストールするためのステップバイステップのチュートリアルを[提供しています](https://learn.microsoft.com/ja-jp/windows/wsl/install)。  これは必須です。ほとんどの開発者はWSL2を使用します。(非常に経験豊富な古参の開発者（グレイビアード）や特定の状況にある開発者は例外です)。

次に、開発環境ツールをインストールする必要があります。ここでもMicrosoftが[チュートリアルを提供しています](https://learn.microsoft.com/ja-jp/windows/wsl/setup/environment)。これによりUbuntuがインストールされますが、今は他のディストリビューションについては考えなくても大丈夫です。

指示についてのいくつかの注記：

-「コードエディタ」のインストールを求められますが、当面は無料のVisual Studio Codeを使用してください。将来的にはさまざまな選択肢があることを学びます。[2]
- Dockerについても言及されていますが、インストールしてください。すぐに必要というわけではありませんが、後で役立ちます。
- まだデータベースやGPUアクセラレーションについて心配する必要はありません。
- WSLコマンドについては学ぶ必要がありますが、それについては後で詳しく説明します。

最後に、[こちらのチュートリアル](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-git)を使用してGitをインストールできます。GitHubアカウントを作成するように提案されても無視してください。 (MicrosoftがGitHubを所有しているため、アカウントを取得するように勧めるのは当然のことです。)また、Git Credential Managerについても、今のところあなたの仕事には関係ないので無視してください。

[2] If someone ever suggests you should install Eclipse, nod politely; however please note that the suggestions makes them untrustworthy.　もし誰かがEclipseのインストールを勧めたら、礼儀正しく反応してください。しかし、その提案をする人は信頼できないことを覚えておいてください。
