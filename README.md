# zabbix-nginx-stats
Nginx monitoring for zabbix

# Intro
Need for nginx server installed with ngx_http_stub_status_module, zabbix agent and curl
Zabbix will parse stub_status page via curl and pass results to zabbix server

# Installation
1. Clone zabbix-nginx-stats repo:
	git clone https://github.com/azatuni/zabbix-nginx-stats.git
2. Move to cloned repo derictory:
	cd zabbix-nginx-stats
3. Copy stub_status configuration to nginx configuration include directory, usually:
	cp nginx_zabbix_agent.conf /etc/nginx/conf.d/
4. Make a configuration test of nginx and restart it:
	nginx -t && service nginx restart
5. Copy zabbix agent configuration file with UserParameters to zabbix agent configuration include directory, usually:
	cp nginx_user_params.conf /etc/zabbix/zabbix_agentd.d/
6. Restart zabbix agent daemon:
	service zabbix-agent restart
7. Import zabbix_template_app_nginx_service.xml to zabbix server UI.
8. Add template to previously configured host via zabbix UI.
