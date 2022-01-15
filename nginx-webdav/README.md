## Nginx with webdav

```bash
git clone https://github.com/arut/nginx-dav-ext-module.git
wget http://tengine.taobao.org/download/tengine-2.3.3.tar.gz
tar zxvf tengine-2.3.3.tar.gz && cd tengine-2.3.3
./configure --with-http_dav_module --add-module=../nginx-dav-ext-module --sbin-path=/usr/local/sbin/nginx  && make -j 16 && make install
htpasswd -c /mdata/web/webdav/.htpasswd webdav
```

```conf
http {
dav_ext_lock_zone zone=davlock:10m;
server {
        server_name dav.msft.io;
        
	root /data/download/video;
        location / {
        autoindex on;

        # autoindex_localtime on;
        set $dest $http_destination;

        # 对目录请求、对URI自动添加"/" 
        if (-d $request_filename) {
                rewrite ^(.*[^/])$ $1/;
                set $dest $dest/;
        }

        # 对MOVE|COPY方法强制添加Destination请求头 
 #      if ($request_method ~ (MOVE|COPY)) {
 #          more_set_input_headers 'Destination: $dest';
 #      }

        if ($request_method ~ MKCOL) {
                rewrite ^(.*[^/])$ $1/ break;
        }

        # webdav config
        client_body_temp_path /tmp;
        dav_methods PUT DELETE MKCOL COPY MOVE; #DAV支持的请求方法
        dav_ext_methods PROPFIND OPTIONS LOCK UNLOCK; # DAV扩展支持的请求方法
        create_full_put_path on;  # 启用创建目录支持
        dav_access group:rw all:r; # 创建文件的以及目录的访问权限
        # auth_basic "Authorized Users Only";
        auth_basic "Authorized Users WebDAV";
        auth_basic_user_file /mdata/web/webdav/.htpasswd;
      }
  }
}
```
