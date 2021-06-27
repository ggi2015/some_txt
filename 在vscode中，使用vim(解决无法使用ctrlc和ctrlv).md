在vscode中，使用vim(解决无法使用ctrlc和ctrlv)

使用vim，但是不用控制键

```
1、打开vscode的设置，搜vim ctrl,取消选择Vim:Use Ctrl Keys
2、打开vscode的设置，搜vim handle,在setting.json中编辑添加：
	"vim.handleKeys": {
        "<C-a>": false,
        "<C-b>": false,
        "<C-c>": false,
        "<C-d>": false,
        "<C-e>": false,
        "<C-f>": false,
        "<C-g>": false,
        "<C-h>": false,
        "<C-i>": false,
        "<C-j>": false,
        "<C-k>": false,
        "<C-l>": false,
        "<C-m>": false,
        "<C-n>": false,
        "<C-o>": false,
        "<C-p>": false,
        "<C-q>": false,
        "<C-r>": false,
        "<C-s>": false,
        "<C-t>": false,
        "<C-u>": false,
        "<C-v>": false,
        "<C-w>": false,
        "<C-x>": false,
        "<C-y>": false,
        "<C-z>": false
    },
//————————————————
//版权声明：本文为CSDN博主「屡次拒绝田馥甄」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
//原文链接：https://blog.csdn.net/weixin_42397018/article/details/105321179
```

