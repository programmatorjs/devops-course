#### 2. Создать именованный пайп (named pipe). Вывести в файл через созданный pipe вывод команды `ss -plnt`
```sh
[root@dev-server ~] mkfifo trully_pipe
[root@dev-server ~] ss -plnt > trully_pipe &
[1] 19477
[root@dev-server ~] cat trully_pipe > output.txt
[1]+  Done                    ss -plnt > trully_pipe
```