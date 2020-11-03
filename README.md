版本：4.0beta

1、合并osgb切片中的节点，对于非同一级别下的数据采用分裂的方式处理

2、支持ENU坐标系

3、支持地理坐标系

4、支持坐标转换

-----------------------------------------------------------------------------

在使用前需要配置gdal库（坐标转换），将目录下面gata-data文件夹复制到电脑（除了c盘，不包含中文目录）中。
在电脑环境变量里面新增 GDAL_DATA,值设置为上一步gata-data文件夹复制的路径。

请在cmd中运行osgb2i3s.exe

        -h 帮助说明（可选）
        
        -i osgb路径输入地址（必须）
        
        -o 生成slpk目录地址（必须）
        
        -n 生成slpk名称（必须）
        
        -m 线程数目（必须）
        
        -p 贴图像素约束，默认是输出最原始贴图，-p 1024超过1024像素的贴图都将被优化（可选）
        
        -t 输入目标坐标系epsg码（可选）启用之后将会带来效率上的降低
        
        -pack （可选）如果不想打包slpk文件，仅保存文件夹的形式
        
        -dds（可选）对现有贴图生成dds压缩
        
        -top（可选）不生成顶级范围节点，默认是开启的
        
        -modify（可选）如果你的数据是二次编辑过的，生成的文件出现贴图混乱的现象，你可以启用这一项来解决该问题

**运行日志文件在生成slpk目录的上一级目录 ，名称叫"logfile.txt"，当你的程序没有运行成功或者得到的结果怪异请查看日志文件，根据日志的提示查看对于数据是否为脏数据

-----------------------------------------------------------------------------

坐标系转换示例：

C:\Users\pengfei\Desktop\osgb2i3s_2_6\tool\osgb2i3s.exe -i D:\osgb2i3s\src\osgb2i3s\osgb2i3s\osgbTestData -o D:\osgb2i3s\src\osgb2i3s\osgb2i3s\export -n model -m 8 -t 4490

普通转换示例：

C:\Users\pengfei\Desktop\osgb2i3s_3_2\tool\osgb2i3s.exe -i D:\osgb2i3s\src\osgb2i3s\osgb2i3s\osgbTestData -o D:\osgb2i3s\src\osgb2i3s\osgb2i3s\export -n model -m 8

****************************************************************注意***************************************************************************************************

1-请在cmd中使用相对路径来运行exe

2-lod控制以效率优先为原则，或许你生成的数据有些模糊，但这种现象可以采用I3S工具集调节一下

3-内部测试版使用权限为1个月,请留邮箱给我

4-对于4326的数据默认会生成3857的投影数据，两者在使用上几乎没有区别

5-请在控制台运行过程中不要点击，容易造成程序暂停，这是由于window控制台本身特性决定，你可以右键控制台将“快速编辑模式”去掉。

6-请使用英文的文件路径
