## SVN Working Copy

- A working copy is `a copy` that has been `checked out to the staging area`.

## SVN Command

- SVN Checkout Command
- SVN Lock Command
- SVN Add Command
- SVN Delete Command
- SVN Commit Command
- SVN Diff Command
- SVN Status Command
- SVN Revert Command
- SVN Resolved Command
- SVN Log Command
- SVN Move Command
- SVN Rename Command
- SVN List Command
- SVN Update Command
- SVN Info Command
- SVN Merge Command

## Checkout Command

- used to `create the working copy of the SVN project`, If the directory `structure is changed, we may need to re-check out it`.

```bash
svn checkout URL
```

---

```bash
svn co URL
```

## Lock Command

- unlock/lock the file

```bash
svn lock -m “lock test file“
```

---

```bash
svn unlock PATH
```

## Info Command

- provides a quick look at the working copy. communicate with the `Local Working Copy`,not a SVN Server.

```bash
svn info
```

## SVN Diff Command

- display the differences between two versions of files,`working copy and the remote copy`(SVN-server). We can find the `two revision,paths`, and more.

```bash
svn diff filename  
```

---

```bash
svn diff -r R1: R2 filename
```

## SVN Status Command

- `displays the status` of the working copy,the repository is `updated, added/deleted, or file is not under revision control,locked` and more.
- ?：不在svn的控制中；M：內容被修改；C：發生沖突；A：預定加入到版本庫；K：被鎖定

```bash
svn status path
```

```bash
svn status -v path
```

-[SVN Status](http://svnbook.red-bean.com/zh/1.6/svn.ref.svn.c.status.html)

## SVN resolve Command

- 移除工作副本的目錄或文件的“沖突”狀態。
- 本子命令`不會依語法來解決沖突或是移除沖突標記`,它只是`移除沖突的相關文件`，然後讓 PATH,可以再次提交。
  
```bash
svn resolved
```

## SVN revert Command

- 恢復原始未改變的工作副本文件 (恢復大部份的本地修改)

```bash
svn revert PATH
```

## SVN Cleanup Command

- 它查找工作拷贝中的所有遗留的日志文件，删除进程中工作拷贝的锁。如果SVN告诉你工作拷贝中的一部分已经`锁定`了，你就需要运行这个命令了

- 这时候无论你在执行SVN的更新、提交等子命令都会
提示“**locked”的错误。一般出现这种情况的解决方法：

> 1.可以使用SVN clean up来清除锁定。
> 2.如果不是本目录锁定，系统提示上一层目录锁定，需要到上一层或者根目录中清除。

### cleanup Memo

- $ svn status
  - L somedir
  - M somedir/foo.c

- $ svn cleanup
- $ svn status
  - M somedir/foo.c

## SVN Log Command

```bash
svn log Path  
```

## SVN List Command

- you want to `view the details of the repository` without making a working copy.

```bash
svn list
```

## SVN Move Command

- the file to the targeted destination. Commit the file to make the changes on the repository.
  
```bash
svn move src dest
```

## SVN Update Command

- svn update no params，default 當前目錄以及子目錄下的所有文件都更新到最新版本
- update the working copy of the project.
- brings the changes from the `working copy to the repository`.
- `matches` the working copy `with the HEAD by default`.
- any changes are made by the other users. We have to update the repository...

> 如果在提交的時候提示過期的話，是因為conflict，需要先update，修改文件，然後清除svn resolved，最後再提交commit)

```bash
svn update path
```

## SVN Merge Command

- used to apply two differences between `two sources to a working path`.
- merge the changes to the `same destination`.

```bash
svn merge SOURCE1[@N] SOURCE2[@M] [TARGET_PATH]  

```

## Memo

> 註：svn status、svn diff和 svn revert這三條命令在沒有網絡的情況下也可以執行的，原因是svn在本地的.svn中保留了本地版本的原始拷貝。
