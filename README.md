## Hướng dẫn cài đặt cho Windows
1. Tải và cài đặt [Ruby cho windows](https://rubyinstaller.org/downloads/)
2. Cài đặt [Git cho windows](https://git-scm.com/downloads/win)
3. Chạy chương trình Git Bash và checkout mã nguồn
   ``` bash
   git clone git@github.com:duyhieubui/tse-2026.git
   ```
4. Mở cửa sổ lệnh `cmd` và di chuyển đến thư mục `tse-2026` và chạy
   các lệnh sau để cài đặt `jekyll`
   ``` sh
   bundle install
   ```

5. Chạy thử nghiệm trang web bằng lệnh sau:
   ``` sh
   bundle exec jekyll serve
   ```
   Terminal sẽ hiện như sau:
 
   ``` text
      C:\Users\dh\work\icdv-conf.org>bundle exec jekyll s
   To use retry middleware with Faraday v2.0+, install `faraday-retry` gem
   Configuration file: C:/Users/duyhieu/work/icdv-conf.org/_config.yml
               Source: C:/Users/duyhieu/work/icdv-conf.org
         Destination: C:/Users/duyhieu/work/icdv-conf.org/_site
   Incremental build: disabled. Enable with --incremental
         Generating...
                     done in 2.035 seconds.
   Please add the following to your Gemfile to avoid polling for changes:
      gem 'wdm', '>= 0.1.0' if Gem.win_platform?
   Auto-regeneration: enabled for 'C:/Users/duyhieu/work/icdv-conf.org'
      Server address: http://127.0.0.1:4000/
   Server running... press ctrl-c to stop.
   ```
6. Truy cập trang web http://127.0.0.1:4000/ để xem trang web thử nghiệm
