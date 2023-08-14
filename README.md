# Telegram-Name-Updating
每60秒，更新一次用户名（last_name）

参考文档：https://docs.telethon.dev/en/stable/
# 运行时可能遇到表情问题，请用小号代码更新表情版本
    pip install --upgrade emoji==1.6.3
# 1. 准备
运行环境：VPS，python3，python3-pip

创建应用：https://my.telegram.org/  只要填App title和Short name即可。获得api_id和api_hash。
# 2.下载Demo小程序到VPS上
	git clone https://github.com/HereNoAg300L/Telegram-Name-Updating.git
	cd Telegram-Name-Updating
# 3. 安装telethon
	pip3 install -r requirements.txt
# 4. 运行Demo小程序
	python3 tg_username_update.py  
# 5. api认证和用户登陆
根据提示输入api_id和api_hash。接着输入手机号和验证码，如果账号开启了二次验，证根据提示再输入二次验证的密码。最后看到 It works! 表明成功了。 默认的是每30秒钟按照一定概率更新一次last name到特定模式。
# 6. 暂时CTRL+C结束小程序，然后重新挂起来在后台运行(在Telegram-Name-Updating文件夹下运行代码)
	nohup python3 tg_username_update.py &

