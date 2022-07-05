# vlmcsd
- Reference:
  [https://github.com/Wind4/vlmcsd](https://github.com/Wind4/vlmcsd)
- Setup
  - Server:
    ```bash
    [root@node2 ~ 13:56]# yum makecache && yum install git gcc make -y
    [root@node2 ~ 13:56]# git clone https://github.com/Wind4/vlmcsd.git && cd vlmcsd && make -j 8 && cd bin && ./vlmcsd
    [root@node2 ~ 13:56]# netstat -antlep | grep 1688
    tcp        0      0 0.0.0.0:1688            0.0.0.0:*               LISTEN      0          12853309   37939/./vlmcsd
    tcp6       0      0 :::1688                 :::*                    LISTEN      0          12853308   37939/./vlmcsd
    ```
    ```shell
     /bin/vlmcs
     Connecting to 127.0.0.1:1688 ... successful
     Sending activation request (KMS V6) 1 of 1  -> 55041-00206-557-033786-03-4108-6002.0000-1412019 (3A1C049600B60076)
    ```

  - Client
    ```powershell
    slmgr /skms <vlmcsd Server IP>
    slmgr /ato   
    ```
> *examples*


  ![image](https://user-images.githubusercontent.com/88020021/162130582-c11d2f88-2547-45aa-b75d-16c72d9bf797.png)
  ![image](https://user-images.githubusercontent.com/88020021/162130660-90f1c24f-e0cd-46a0-8aa9-d899731926d2.png)
  ![image](https://user-images.githubusercontent.com/88020021/162130721-6f07b157-e9e6-41fb-9dd4-42e064e0d2a6.png)
  ![image](https://user-images.githubusercontent.com/88020021/162130881-3ac7509c-b8b0-45a2-aa14-f0ec1c44cced.png)




