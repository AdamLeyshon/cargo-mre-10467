Tested with Cargo:
    
    # cargo -Vv
    release: 1.69.0
    commit-hash: 6e9a83356b70586d4b77613a6b33f9ea067b9cdf
    commit-date: 2023-04-12
    host: x86_64-unknown-linux-gnu
    libgit2: 1.5.0 (sys:0.16.0 vendored)
    libcurl: 7.86.0-DEV (sys:0.4.59+curl-7.86.0 vendored ssl:OpenSSL/1.1.1q)
    os: Manjaro 22.1.1 (Talos) [64-bit]

Git version is 
    
    # git -v
    git version 2.40.1

My `~/.gitconfig` file:

    # cat ~/.gitconfig 
    [user]
    name = Adam Leyshon
    email = aleyshon@thecodecache.net

The output from `RUST_LOG=trace cargo build`

    cargo build
    Updating git repository `ssh://git@github.com/AdamLeyshon/cargo-mre-10467.git`
    error: failed to get `example-lib` as a dependency of package `example-bin v0.1.0 (/home/aleyshon/source/tcc-src/cargo-ssh-mre/example-bin)`
    
    Caused by:
    failed to load source for dependency `example-lib`
    
    Caused by:
    Unable to update ssh://git@github.com/AdamLeyshon/cargo-mre-10467.git
    
    Caused by:
    failed to fetch into: /home/aleyshon/.cargo/git/db/cargo-mre-10467-cd8c94d9cdb533f4
    
    Caused by:
    failed to authenticate when downloading repository
    
    * attempted ssh-agent authentication, but no usernames succeeded: `git`
    
    if the git CLI succeeds then `net.git-fetch-with-cli` may help here
    https://doc.rust-lang.org/cargo/reference/config.html#netgit-fetch-with-cli
    
    Caused by:
    error authenticating: no auth sock variable; class=Ssh (23)

