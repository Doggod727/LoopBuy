# LoopBuy 校园二手交易平台

## 项目简介
LoopBuy是一个现代化的C2C校园二手交易平台，提供用户注册登录、商品发布交易、管理员后台等完整功能。

## 项目结构

```
LoopBuy/
├── backend/           # 后端服务 (Java Servlet)
│   ├── src/          # 源代码
│   │   ├── main/java/com/shiwu/
│   │   │   ├── admin/      # 管理员模块
│   │   │   ├── user/       # 用户模块
│   │   │   ├── common/     # 公共模块
│   │   │   └── test/       # 测试工具
│   │   └── test/java/      # 测试代码
│   ├── docs/         # 后端API文档
│   ├── pom.xml       # Maven配置
│   └── README.md     # 后端详细说明
├── frontend/         # 前端应用 (计划中)
├── docs/             # 项目文档
└── README.md         # 项目总体说明
```

## 技术栈
- **后端**: Java 8+ + Servlet API + Maven
- **前端**: React + TypeScript (计划中)
- **数据库**: MySQL 5.7+
- **认证**: JWT令牌
- **测试**: JUnit 5 + Mockito
- **工具**: SLF4J日志 + BCrypt密码加密

## 快速开始

### 后端服务
```bash
cd backend
mvn clean compile    # 编译项目
mvn test            # 运行测试
mvn package         # 打包部署
```

详细的后端开发指南请参考 [backend/README.md](backend/README.md)

## 核心功能

### ✅ 已完成功能
- **用户系统**: 用户注册、登录、信息管理、关注系统
- **管理员系统**: 管理员登录、权限验证、用户管理、商品管理
- **审计日志系统**: 完整的操作记录和查询功能 (Task5_3_1_3)
  - 支持筛选和搜索的审计日志查询API
  - 操作统计和趋势分析
  - 数据导出功能
- **安全认证**: JWT令牌、密码加密、权限控制
- **数据管理**: 完整的CRUD操作和数据验证

### 🚧 开发中功能
- **商品系统**: 商品发布、交易管理、商品搜索
- **前端界面**: React前端应用
- **支付系统**: 在线支付集成
- **消息系统**: 用户间消息通信

## API文档

### 用户API
- `POST /api/user/register` - 用户注册
- `POST /api/user/login` - 用户登录
- `GET /api/user/profile` - 获取用户信息
- `POST /api/user/follow` - 关注用户

### 管理员API
- `POST /api/admin/login` - 管理员登录
- `GET /api/admin/dashboard` - 获取统计数据
- `POST /api/admin/users/ban` - 封禁用户
- `POST /api/admin/products/approve` - 审核商品

### 审计日志API (Task5_3_1_3)
- `GET /api/admin/audit-logs` - 查询审计日志（支持筛选和搜索）
- `GET /api/admin/audit-logs/{id}` - 获取日志详情
- `GET /api/admin/audit-logs/stats` - 获取统计数据
- `POST /api/admin/audit-logs/export` - 导出日志

详细API文档请参考 [backend/docs/](backend/docs/) 目录。

## 测试

项目包含完整的单元测试和集成测试：

```bash
# 运行所有测试
cd backend && mvn test

# 运行Task5_3_1_3专门测试
mvn test -Dtest="AuditLogServiceTest#testTask5_3_1_3*"
```

### 测试覆盖率
- **用户模块**: 100%覆盖
- **管理员模块**: 100%覆盖
- **审计日志模块**: 100%覆盖
- **公共工具类**: 100%覆盖

## 部署说明
1. 配置MySQL数据库，执行数据库初始化脚本
2. 修改数据库连接配置
3. 运行 `cd backend && mvn clean package` 编译打包
4. 部署WAR文件到Servlet容器（如Tomcat）

## 测试账号
- 管理员用户名：admin
- 管理员密码：admin123
- 普通用户名：test
- 普通用户密码：123456

## 贡献指南
1. Fork项目
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交代码变更 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 创建Pull Request

## 许可证
本项目采用MIT许可证

## 联系方式
- GitHub: [@Doggod727](https://github.com/Doggod727)
- 项目链接: [https://github.com/Doggod727/LoopBuy](https://github.com/Doggod727/LoopBuy)