This is a cargo fork.  https://github.com/rust-lang/cargo 。I only modifiy a little to add a function to let cargo can custom translate more attributes （cfgs) to rustc.   

In the Cargo.toml. write cfgs  like this
[cfgs]
tt = "tt"

will be work in main.rs. like features will give rustc the parameters  "--cfg tt="tt"" . and all dependences will have this cfg attributes. It's like c++ predefintion。

#[cfg(tt = "tt")]
fn printtt() {
    println!("cfg tt=tt");
}

