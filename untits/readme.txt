1.New a python project 
2.cd %project.home%
3.运行setup.bat创建venv虚拟环境 (注意内网运行setup.py需要手动将requirements.txt需要的安装包下载下到dependency目录(pip download -d ./dependency -r requirements.txt),外网直接运行）
4。等待安装结束重新打开projecth环境默认引用了interpreter无异常显示，否则手动配置刚才创建的venv/Scripts/python.exe；
