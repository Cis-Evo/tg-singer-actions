# tg-singer-actions
使用[tg-signer](https://github.com/amchii/tg-signer)通过github action实现每日自动化签到

# 使用方法
1. fork本仓库并在你自己的仓库完成后续步骤
2. 修改`.github/workflows/main.yml`中的`on.schedule.cron`来指定每日运行时间
3. 在仓库中设置以下repository secrets：
    a. `SESSION_STRINGS`：多个session用如下格式填入，单行，例如：
       ```
       ["session_string_0","session_string_1","session_string_2"]
       ```
       单账号时填入单个引号串即可：`"your_session_string"`
    b. `TASK_MAP`：任务配置JSON，格式见`TASK_MAP_DEMO.json`。
       每个任务可通过本地tg-signer设置好后获取配置，并在其中添加`session_index`字段指定使用第几个session（从0计数，缺省为0）
4. 测试action
