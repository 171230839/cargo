This is a cargo fork.  https://github.com/rust-lang/cargo 。I only modifiy a little to add a function to let cargo can custom translate more attributes （cfgs) to rustc.   

In the Cargo.toml. write cfgs  like this
[cfgs]
tt = "tt"

will be work in main.rs. like features will give rustc the parameters  "--cfg tt="tt"" . and all dependences will have this cfg attributes. It's like c++ predefintion。

#[cfg(tt = "tt")]
fn printtt() {
    println!("cfg tt=tt");
}


cargo.toml 中的 features 无法传入 tt=“tt” 这样的键值对， 而且似乎无法将输入的features 传入所有的依赖性。 而是要在 .toml 文件中[dependencies]🔝指定 依赖项使用的feature, 十分别扭。 简单的修改了下。 让 rust的cfg 属性功能充分使用起来， 当然只是简单修改，没有深度完善， 需小心使用。

