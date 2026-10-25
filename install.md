我是使用MacBook  
Step 1   
開啟RUST的官網，複製 `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`  

<img width="728" height="521" alt="Screenshot 2026-10-23 at 20 55 14" src="https://github.com/user-attachments/assets/b926e6b6-d60f-4197-9dbf-9f2aaab5cb7f" />
<img width="1911" height="728" alt="Screenshot 2026-10-23 at 20 56 39" src="https://github.com/user-attachments/assets/4a663c04-2647-4d6d-ad33-a4661983d407" />

Step 2  
開啟終端機，貼上剛剛複製的指令，並執行  
Step 3  
選擇１）預設的安裝  
(那我個人是有遇到安裝失敗的情形，原因是新版的 macOS 預設 Shell 其實是 Zsh（設定檔是 ~/.zshrc），而不是 ~/.bash_profile。如果你的終端機其實在跑 Zsh，但安裝程式去改 .bash_profile 失敗，或是改錯地方，就會出問題。  
後來我就按照gemeni的指導，指令改成`curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- --no-modify-path`，就是加上 --no-modify-path 參數，讓安裝程式不要去動會報錯的 .bash_profile  
安裝完成後，執行以下指令把環境變數寫進你的 ~/.zshrc，執行這個指令`echo 'source "$HOME/.cargo/env"' >> ~/.zshrc`，但執行這行失敗，因為權限不足，所以我們需要再執行這行指令`sudo chown $(whoami) ~/.zshrc`，並補上寫入的權限`chmod u+w ~/.zshrc`  
重新將 Rust 加入 Zsh 設定檔：`echo 'source "$HOME/.cargo/env"' >> ~/.zshrc`  
套用設定並確認是否安裝成功  
```
source ~/.zshrc  
rustc --version  
cargo --version
```
成功了話，就會看到這樣
<img width="269" height="32" alt="Screenshot 2026-10-23 at 21 28 19" src="https://github.com/user-attachments/assets/3cd8bea3-1fd2-4600-b1c0-ac75447bcf6e" />
