# Telegram-Name-Updating
每60秒，更新一次用户名（last_name）

参考文档：https://docs.telethon.dev/en/stable/
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
# 6. 进程守护
	mkdir /usr/lib/systemd/system
service配置(以下代码要全部一起复制粘贴过去)

	cat > /usr/lib/systemd/system/timebot.service << EOF
	[Unit]
	Description=Telegram-Name-Updating daemon
	After=network.target
	
	[Install]
	WantedBy=multi-user.target
	
	[Service]
	Type=simple
	WorkingDirectory=/opt/Telegram-Name-Updating
	ExecStart=/usr/bin/python3 tg_username_update.py
	Restart=always
	
	EOF

# 7. 启动bot
        systemctl daemon-reload && systemctl start timebot && systemctl enable timebot
