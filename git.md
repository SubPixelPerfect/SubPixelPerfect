# GIT 

To push as different user  [link](https://medium.com/@bivil/you-can-configure-an-individual-repo-to-use-a-specific-user-email-address-which-overrides-the-6e5f6521d5c9)

```bash
cd "git/root"
# set different user info
git config user.name "Your Name1"
git config user.email your@email1.com

#or using editor
git config -e

# ensure that local and global values are different
git config --local -l
git config --global -l
```





## Hello GitHub

1. Go to github and create repo named youname.github.io

2. Crate file `index.html`

   ```html
   <!DOCTYPE html>
   <html>
       <body>
           <h1>Hello World</h1>
           <p>I'm hosted with GitHub Pages.</p>
       </body>
   </html>
   ```

3. Ste is up on youname.github.io

## Jekyll

Install a **Ruby+Devkit** version from [RubyInstaller Downloads](https://rubyinstaller.org/downloads/).

crate `_config.yml`

```yml
repository: SubPixelPerfect/SubPixelPerfect.github.io
```

and `gemfile`

```ruby
source "https://rubygems.org"
gem "github-pages", group: :jekyll_plugins

# Performance-booster for watching directories on Windows
gem "wdm", "~> 0.1.0" if Gem.win_platform?
```

run `bundle install`
run `bundle exec jekyll serve`

local site is up on http://127.0.0.1:4000

