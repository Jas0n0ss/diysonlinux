# vlmcsd
- Reference:
  [https://github.com/Wind4/vlmcsd](https://github.com/Wind4/vlmcsd)
- Setup
  - Server:
    ```shell
    yum makecache && yum install git gcc make -y
    git clone https://github.com/Wind4/vlmcsd.git && cd vlmcsd && make -j 8
    cd bin && ./vlmcsd
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
    
