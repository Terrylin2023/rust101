我們就來寫hello world（每個程式語言的第一支程式基本上好像都是他）
我是用vscode，大家就看自己熟悉用什麼，然後建立一個新的資料夾，在vscode開啟一個新的terminal（在左上角有個叫終端機），輸入`cargo new [專案名稱]`，所以我的話是輸入 `cargo new hello`，這個是在每次第一次建立專案的時候使用，
指令輸入後會看到他建立了新的資料夾**hello**在你剛剛開的資料夾底下(正常你要看到他底下有一些檔案，比如：cargo.toml,cargo.lock,etc.)，然後我們就在hello資料夾下建立一個新的檔案，就叫**main.rs**，
就可以在右邊輸入
```
fn main () {
    println!("Hello, world!");
}
```
按下command+s(儲存檔案)，回到底下的terminal，輸入：`cargo run`
正常就會看到
<img width="537" height="61" alt="Screenshot 2026-10-25 at 11 40 01" src="https://github.com/user-attachments/assets/6e17665a-b47b-4a47-86d9-60d740e9e4b8" />

附贈gemini的貼心體醒
💡 建議的日常 Rust 開發習慣
以後寫 Rust 專案，你只需要記住三個最常用的 Cargo 指令：

`cargo new [專案名稱]`：建立新專案（只做一次）

`cargo run`：編譯並執行（寫完扣、想看結果時用這個）

`cargo check`：快速檢查程式碼有沒有寫錯（不用真正編譯，速度極快）
