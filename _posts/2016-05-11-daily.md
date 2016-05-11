---
layout: post
title:  "linux shell"
date:   2016-05-11 20:38:18 +0800
---

shell Bash测试
:test expr and [expr]
-eq、 -ne、-lt、 -le、 -gt 或 -ge 比较算术值，它们分别表示等于、不等于、小于、小于等于、大于、大于等于。
分别用操作符 =、 !=、< 和 > 比较字符串是否相等、不相等或者第一个字符串的排序在第二个字符串的前面或后面。单目操作符 -z 测试 null 字符串，如果字符串非空 -n 返回 True（或者根本没有操作符）
注意：shell 也用 < 和 > 操作符进行重定向，所以必须用 \< 或 \> 加以转义。
如：
[ian@pinguino ~]$ [ "abc" \< "def" ];echo $?
0
详情参考：http://www.ibm.com/developerworks/cn/linux/l-bash-test.html


参数：
详情：http://www.ibm.com/developerworks/cn/linux/l-bash-parameters.html
getopts命令
while getopts ":v:p:" optval "$@"
  do
    case $optval in
      "v")
        ssversion="$OPTARG"
      ;;
      "p")
        # Convert any backslashes to forward slashes
        pathsuffix="${OPTARG//\\//}"
        # Ensure this is a leading / and no trailing one
        [ ${pathsuffix:0:1} != "/" ] && pathsuffix="/$pathsuffix"
        pathsuffix=${pathsuffix%/}
        # Strip off the last hyphen and what follows
        dateprefix=${pathsuffix%-*}
        # Use the length of what remains to get the hyphen and what follows
        [ "$dateprefix" != "$pathsuffix" ] && datesuffix="${pathsuffix:${#dateprefix}}"
        ;;
      *)
        errormsg="Unknown parameter or option error with option - $OPTARG"
        ;;
    esac
  done



