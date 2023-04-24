# 魅族固件解包，提取apk
1、下载固件，https://flyme.cn/firmware.html  
2、从update.zip当中解压出payload.bin  
3、解包，python payload_dumper.py --out path_to_output payload.bin，https://github.com/vm03/payload_dumper  
这一步获得的是多个image文件，需要注意其中大部分是erofs格式的镜像，需要unpack或者以erofs格式挂载  
4、unpack，在linux下执行erofsUnpackKt_x64 path_to_img_file，https://github.com/thka2016/erofsUnpack  
这一步直接将image解压到文件夹中  
5、复制apk，写个脚本从vendor、product、system、system_ext目录下将所有.apk文件复制到指定目录  
