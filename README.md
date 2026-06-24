## Hướng dẫn cài đặt cho Windows
1. Tải và cài đặt [Ruby cho windows](https://rubyinstaller.org/downloads/)
2. Cài đặt [Git cho windows](https://git-scm.com/downloads/win)
3. Chạy chương trình Git Bash và checkout mã nguồn
   ``` bash
   git clone git@github.com:duyhieubui/icdv-conf.org.git
   ```
4. Mở cửa sổ lệnh `cmd` và di chuyển đến thư mục `icdv-conf.org` và chạy
   các lệnh sau để cài đặt `jekyll`
   ``` sh
   bundle install
   gem install s3_website
   ```
   Để sử dụng s3_website cần phải cài đặt [OpenJDK 8](https://builds.openlogic.com/downloadJDK/openlogic-openjdk/8u442-b06/openlogic-openjdk-8u442-b06-windows-x64.msi)

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

## Upload nội dung website lên internet

1. Chạy lệnh sau để biên dịch mã nguồn và sinh mã html bằng cách chạy các lệnh sau trong cửa sổ dòng lệnh
   ```sh
   bundle exec jekyll clean
   bundle exec jekyll build
   ```

   Cửa sổ dòng lệnh sẽ hiển thị như sau:

   ``` text
      C:\Users\dh\work\icdv-conf.org>bundle exec jekyll clean
   To use retry middleware with Faraday v2.0+, install `faraday-retry` gem
   Configuration file: C:/Users/duyhieu/work/icdv-conf.org/_config.yml
            Cleaner: Removing C:/Users/duyhieu/work/icdv-conf.org/_site...
            Cleaner: Nothing to do for C:/Users/duyhieu/work/icdv-conf.org/.jekyll-metadata.
            Cleaner: Removing C:/Users/duyhieu/work/icdv-conf.org/.jekyll-cache...
            Cleaner: Nothing to do for .sass-cache.

   C:\Users\dh\work\icdv-conf.org>bundle exec jekyll build
   To use retry middleware with Faraday v2.0+, install `faraday-retry` gem
   Configuration file: C:/Users/duyhieu/work/icdv-conf.org/_config.yml
               Source: C:/Users/duyhieu/work/icdv-conf.org
         Destination: C:/Users/duyhieu/work/icdv-conf.org/_site
   Incremental build: disabled. Enable with --incremental
         Generating...
                     done in 1.935 seconds.
   Auto-regeneration: disabled. Use --watch to enable.
   ```
2. Upload nội dung website lên Amazon S3 & Cloudfront
   ```sh
   s3_website push
   ```

   Cửa sổ dòng lệnh thông báo đã nạp file thành công:

   ``` text
   C:\Users\duyhieu\work\icdv-conf.org>s3_website push
   openjdk version "1.8.0_372"
   OpenJDK Runtime Environment (Temurin)(build 1.8.0_372-b07)
   OpenJDK 64-Bit Server VM (Temurin)(build 25.372-b07, mixed mode)
   [info] Deploying C:\Users\duyhieu\work\icdv-conf.org\_site/* to icdv-conf.org
   [succ] Updated humans.txt (text/plain; charset=utf-8)
   [succ] Updated sitemap.xml (application/xml)
   [succ] Updated atom.xml (application/xml)
   [succ] Invalidated 1 item on CloudFront
   [info] Summary: Updated 3 files. Transferred 8.0 kB, 15.0 kB/s.
   [info] Successfully pushed the website to http://icdv-conf.org.s3-website-us-east-1.amazonaws.com
   ```
