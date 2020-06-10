# osgb-slpk
osgb转slpk（目前最新版为3.8（i3s1.7）版本，仅供内部测试）
版本号3.6 
使用说明：
----------------------------------------------------------------------------
版本：2.4增加贴图压缩
2.5修复内存泄露问题
2.6增加报错日志输出
2.7增加坐标系转换
2.8修复bug
2.9修复bug
3.0封装
3.1修复bug
3.2因为osgb命令不规范，去除级别筛选功能
3.3修复升级工具报错
3.4暴露贴图压缩接口，允许客户使用不压缩或者自定义压缩图片
3.5支持ENU开头和自定义坐标系文件的数据转换

---------------------------------------------------------------------------------------------------
在使用前需要配置gdal库（坐标转换），将目录下面gata-data文件夹复制到电脑（除了c盘，不包含中文目录）中。
在电脑环境变量里面新增 GDAL_DATA,值设置为上一步gata-data文件夹复制的路径。

请在cmd中运行osgb2i3s.exe
        -h 帮助说明
        -i osgb路径输入地址
        -o 生成slpk目录地址
        -n 生成slpk名称
        -m 线程数目
        -t 输入目标坐标系epsg码（可选）
运行日志文件在生成slpk目录的上一级目录 ，名称叫"log.txt"

-----------------------------------------------------------------------------
坐标系转换示例：
C:\Users\pengfei\Desktop\osgb2i3s_2_6\tool\osgb2i3s.exe -i D:\osgb2i3s\src\osgb2i3s\osgb2i3s\osgbTestData -o D:\osgb2i3s\src\osgb2i3s\osgb2i3s\export -n model -m 8 -t 4490
普通转换示例：
C:\Users\pengfei\Desktop\osgb2i3s_3_2\tool\osgb2i3s.exe -i D:\osgb2i3s\src\osgb2i3s\osgb2i3s\osgbTestData -o D:\osgb2i3s\src\osgb2i3s\osgb2i3s\export -n model -m 8

*****************注意*************************
因为本人时间有限，为了提升前端加载效率，请使用i3s_convert工具升级到最新版本slpk。
后续我会有时间在程序里面直接输出i3s 1.7

*****************升级操作说明：********************
	1、将i3s_convert.exe复制到slpk目录
	2、cmd中cd 切换到i3s_convert.exe目录
	3、敲击i3s_convert.exe -u input.slpk -o model.slpk -x 命令
