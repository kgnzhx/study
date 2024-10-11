# 2024/10/11

## Linux操作命令

1. ls -a 显示隐藏文件

2. ls -l 显示文件并显示文件权限

3. 读取“-”开头的文件，或“-”命名的文件，必须指定文件的完整位置，”.“表示当前目录，“..”表示上级目录

4. 如要读取“-”开头的或命名的文件，使用命令cat ./-或者cat < - 重定向文件

5. 进入含有空格特殊符号的目录，使用\转义符转义或使用“”引号将其括起来，如file name inhere ,进入该目录则使用命令cd "file name inhere"或者cd file\ name\ inhere,该操作适用于读取cat，创建文件夹mkdir ,创建文件touch,复制cp,
6. file命令可以用来识别文件类型，如file ./*，识别当前目录下的所有文件类型
7. find 命令可使用参数指定查找文件，如find -type f -size 1002c,查找普通文件大小为1002字节的文件。find查询命令参见https://www.runoob.com/linux/linux-comm-find.html

