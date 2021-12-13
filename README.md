
该工具集旨在提高osgb转换slpk成功率，只进行了简单的节点优化处理。
如果你需要对大数据量的倾斜效率进行优化，那么配套的优化工具是个不错的选择，请根据需要选择使用！

release版本：2.1

1、合并osgb切片中的节点，对于非同一级别下的数据采用分裂的方式处理

2、支持ENU坐标系

3、支持地理坐标系

4、容错大量空节点数据

-----------------------------------------------------------------------------

工具可以直接使用cmd，请查看对应的操作文档或者cmd中命令行帮助


**运行日志文件在生成slpk目录的上一级目录 ，名称叫"logfile.txt"，当你的程序没有运行成功或者得到的结果怪异请查看日志文件，根据日志的提示查看对于数据是否为脏数据

-----------------------------------------------------------------------------

转换示例：

C:\Users\Desktop\osgb2i3s_2_6\tool\osgb2i3s.exe -osgb -i D:\osgb2i3s\src\osgb2i3s\osgb2i3s\osgbTestData -o D:\osgb2i3s\src\osgb2i3s\osgb2i3s\export.slpk -m 8


****************************************************************注意***************************************************************************************************

1-lod控制以效率优先为原则，或许你生成的数据有些模糊，但这种现象可以采用I3S工具集调节一下

2-内部测试版使用权限为12个月,请留邮箱给我(邮箱：2283847787@qq.com)

3-对于4326的数据默认会生成3857的投影数据，两者在使用上几乎没有区别

4-请在控制台运行过程中不要点击，容易造成程序暂停，这是由于window控制台本身特性决定，你可以右键控制台将“快速编辑模式”去掉。

5-请使用英文的文件路径
