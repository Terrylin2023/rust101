我是使用MacBook
Step 1 
開啟RUST的官網，複製 `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`
Step 2
開啟終端機，貼上剛剛複製的指令，並執行
Step 3
選擇１）預設的安裝
(那我個人是有遇到安裝失敗的情形，原因是新版的 macOS 預設 Shell 其實是 Zsh（設定檔是 ~/.zshrc），而不是 ~/.bash_profile。如果你的終端機其實在跑 Zsh，但安裝程式去改 .bash_profile 失敗，或是改錯地方，就會出問題。
後來我就按照gemeni的指導，指令改成`curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- --no-modify-path`，就是加上 --no-modify-path 參數，讓安裝程式不要去動會報錯的 .bash_profile
安裝完成後，執行以下指令把環境變數寫進你的 ~/.zshrc，執行這個指令`echo 'source "$HOME/.cargo/env"' >> ~/.zshrc`，但執行這行失敗，因為權限不足，所以我們需要再執行這行指令`sudo chown $(whoami) ~/.zshrc`，補上寫入的權限`chmod u+w ~/.zshrc`
重新將 Rust 加入 Zsh 設定檔：`echo 'source "$HOME/.cargo/env"' >> ~/.zshrc`
套用設定並確認是否安裝成功
`
source ~/.zshrc
rustc --version
cargo --version
`
