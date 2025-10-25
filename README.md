## 代码结构树
```
tree -L 3 .
.
├── console
│   ├── config
│   │   ├── install_agent.tpl
│   │   ├── permission.json
│   │   ├── setup
│   │   └── system_config.tpl
│   ├── data
│   └── logs
└── easysearch
    ├── config
    │   ├── admin.crt
    │   ├── admin.key
    │   ├── analysis-ik
    │   ├── ca.crt
    │   ├── ca.key
    │   ├── easysearch.yml
    │   ├── easysearch.yml.example
    │   ├── instance.crt
    │   ├── instance.key
    │   ├── jvm.options
    │   ├── jvm.options.d
    │   ├── log4j2.properties
    │   └── security
    ├── data
    └── logs
```

my-vault-app/
├── src/
│   ├── App.tsx              # 主组件，初始化 Telegram WebApp
│   ├── components/
│   │   └── Vault.tsx        # 仓库组件，包含密码验证和数据展示
│   ├── index.css            # 全局样式
│   ├── main.tsx             # 入口文件
├── vite.config.ts           # Vite 配置
├── package.json             # 项目依赖和脚本
├── netlify.toml             # Netlify 部署配置文件
├── .gitignore               # Git 忽略文件

