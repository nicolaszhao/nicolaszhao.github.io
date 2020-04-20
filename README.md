# nicolaszhao.com
赵不寒的网络日记，在这里记录着自己的随想、随感和技术学习日志

## 本地预览

### 安装依赖环境

#### Command Line Tools

```
xcode-select --install
```

#### Ruby

```
# You should install Homebrew first.
brew install ruby
# add brew ruby path to shell config
echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> ~/.bash_profile
# check it
ruby -v
```

#### Jekyll

```
# bundler & jekyll
sudo gem install --user-install bundler jekyll
```

#### 参考

* https://jekyllrb.com/docs/installation/macos/
* https://jekyllrb.com/docs/upgrading/

### 运行本地环境

```shell
bundle exec jekyll serve
```

