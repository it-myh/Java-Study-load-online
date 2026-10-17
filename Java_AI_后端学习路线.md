# Java + AI 后端开发学习路线（附配套学习资源）

> 面向人群：编程基础一般、想转行/进阶后端开发，且希望业务里能落地「AI 模块」（如智能问答、RAG 检索、AI Agent）的同学。
> 路线定位：**以 Java 后端为骨架，AI 作为加在业务上的能力模块**，而不是让你去做算法研究或训练大模型。
> 建议节奏：每天 2~3 小时、周末 4~6 小时，全职学习可整体缩短一半。

---

## 0. 路线总览（一张图看懂）

```
第一阶段  编程入门 + 工具链          (2~3 周)
第二阶段  Java 语言基础             (6~8 周)
第三阶段  Java 进阶（JVM/并发/网络） (6~8 周)
第四阶段  数据库（MySQL/Redis）      (4~6 周)
第五阶段  后端框架核心（Spring 全家桶）(8~10 周)
第六阶段  工程化 + 中间件（Git/MQ/微服务）(6~8 周)
第七阶段  数据结构算法 + 计算机基础   (贯穿全程，随进度穿插)
第八阶段  AI 基础认知               (4~6 周，可与第六阶段并行)
第九阶段  大模型应用开发（Prompt/RAG/Agent）(6~8 周)
第十阶段  Java + AI 实战集成（Spring AI / LangChain4j）(6~8 周)
第十一阶段 综合项目实战              (8 周以上，边做边补)
第十二阶段 求职准备（简历/八股/项目复盘）(贯穿 + 最后 4 周冲刺)
```

**关键提示**：第七阶段（算法 + 计算机基础）不要一开始就死磕，建议从第二阶段起就「每周固定几小时」穿插推进，最后阶段再集中刷题。第八阶段（AI 认知）也可以提前看科普视频，降低后期理解成本。

---

## 第一阶段：编程入门 + 工具链（2~3 周）

**目标**：能独立用 IDE 写出、编译、运行一个 Java 程序，会用 Git 和命令行，建立「写代码—调试—看报错」的基本习惯。

**学什么**：
- 计算机如何运行程序（编译 vs 解释，JVM 是什么）
- JDK 安装与环境变量（推荐直接装 **JDK 17 或 21 LTS**，公司主流；个人练习可用 21）
- IntelliJ IDEA 使用（快捷键、断点调试）
- Git 基础（clone / add / commit / push / 分支）
- 命令行基础（Windows 下可用 Git Bash 或 WSL）

**确定的学习资源**：
| 内容 | 资源 | 说明 |
|---|---|---|
| JDK 下载 | [Adoptium (Eclipse Temurin)](https://adoptium.net/) 或 Oracle 官网 | 选 LTS 版本，国内镜像更快 |
| IDE | IntelliJ IDEA 社区版（免费） | [官网下载](https://www.jetbrains.com/idea/download/) |
| Java 环境搭建 + 第一个程序 | 韩顺平《零基础学 Java》前几集（B 站免费） | 讲得慢、适合零基础 |
| Git 入门 | 廖雪峰 [Git 教程](https://liaoxuefeng.com/books/git/introduction/index.html)（免费网站） | 边看边敲命令 |
| 命令行 | B 站搜「Linux 命令入门」/《鸟哥的 Linux 私房菜》前几章 | 只学常用命令即可 |

**检验标准**：用 IDEA 新建项目跑通 `Hello World`；在 GitHub/Gitee 建一个仓库，用 Git 把代码推上去。

---

## 第二阶段：Java 语言基础（6~8 周）

**目标**：掌握 Java 语法、面向对象思想、常用类库，能独立写小型控制台程序。

**学什么（按顺序）**：
1. 变量、数据类型、运算符、流程控制
2. 数组、字符串（String / StringBuilder）
3. 面向对象三特性：封装、继承、多态
4. 抽象类、接口、内部类、枚举
5. 异常处理
6. 集合框架（List / Map / Set，HashMap 原理要有概念）
7. 泛型、Lambda 表达式、Stream API
8. IO 流、文件操作
9. 常用类（日期时间、BigDecimal、Optional）

**确定的学习资源**：
| 内容 | 资源 | 说明 |
|---|---|---|
| 主课程（零基础） | 韩顺平《零基础学 Java》B 站全集 | 免费，讲得细致，适合基础一般的人，可 1.5 倍速 |
| 主课程（偏快/项目向） | 黑马程序员《Java 基础》B 站 | 免费，节奏更快，配套练习多 |
| 文字教程（查漏） | 廖雪峰 [Java 教程](https://liaoxuefeng.com/books/java/introduction/index.html)（免费网站） | 适合当工具书查阅 |
| 参考书（进阶补充） | 《Java 核心技术·卷 I》（Cay Horstmann） | 经典，不要求从头读完，当字典 |
| 刷题巩固 | 牛客网 Java 基础题库 / [Nowcoder](https://www.nowcoder.com/) | 每学完一节做几道 |

**检验标准**：不看视频独立写出「学生管理系统」「简易记账本」这类控制台小项目；能说出 `ArrayList` 和 `LinkedList` 的区别、`==` 与 `equals` 的区别。

---

## 第三阶段：Java 进阶（6~8 周）

**目标**：理解 JVM 内存模型、并发编程、反射、网络编程——这是面试高频 + 写高质量后端代码的底气。

**学什么**：
1. 反射、注解、动态代理（理解 Spring 的基石）
2. JVM：运行时数据区、垃圾回收、类加载机制
3. 并发：线程基础、锁、`synchronized`、`volatile`、线程池、JUC 常用类
4. 网络编程：Socket、BIO/NIO 概念、HTTP 协议基础
5. 设计模式（常见 8~10 个：单例、工厂、策略、观察者等）

**确定的学习资源**：
| 内容 | 资源 | 说明 |
|---|---|---|
| JVM | 《深入理解 Java 虚拟机》（周志明） | 面试必读，可先看第三版核心章节 |
| 并发 | 《Java 并发编程的艺术》 或 黑马程序员并发专题（B 站） | 书 + 视频结合 |
| 反射/注解/动态代理 | 尚硅谷 / 黑马 Java 进阶视频（B 站） | 跟着敲代码 |
| 网络 + HTTP | 《图解 HTTP》（上野宣） | 薄、通俗，快速建立 HTTP 概念 |
| 设计模式 | 《Head First 设计模式》或 B 站「尚硅谷设计模式」 | 重在理解思想，不要求全背 |

**检验标准**：能画出 JVM 内存结构图并解释每个区域；能手写一个简单线程池思路；能说清 `synchronized` 的锁升级过程（面试重点）。

---

## 第四阶段：数据库（4~6 周）

**目标**：会写 SQL、会设计表结构、会用 Redis 缓存，这是后端岗位的基本功。

**学什么**：
1. MySQL：增删改查、聚合、子查询、多表连接
2. 索引原理（B+ 树）、事务与隔离级别、锁
3. SQL 优化、慢查询、Explain 分析
4. 表设计：三大范式、反范式、常见业务建模
5. Redis：五种数据类型、持久化、缓存穿透/击穿/雪崩、分布式锁概念

**确定的学习资源**：
| 内容 | 资源 | 说明 |
|---|---|---|
| MySQL 入门 | 尚硅谷《MySQL 基础》B 站 | 免费，配套练习 |
| MySQL 进阶 | 《MySQL 实战 45 讲》（极客时间，丁奇） | 讲得深，面试高频，价格中等 |
| Redis | 尚硅谷 / 黑马《Redis》B 站 | 免费 |
| 参考书 | 《Redis 设计与实现》（黄健宏） | 配合视频理解原理 |

**检验标准**：能独立设计「订单 + 用户 + 商品」三张表并写出常见业务 SQL；能解释「为什么用索引会快」「什么是事务隔离级别」。

---

## 第五阶段：后端框架核心（8~10 周）

**目标**：掌握企业级后端的主流技术栈 Spring 全家桶，能开发 RESTful API。

**学什么（按顺序）**：
1. Maven / Gradle 构建工具（依赖管理）
2. Spring 核心：IoC 容器、DI、Bean 生命周期
3. Spring MVC：请求处理、参数绑定、拦截器、统一异常处理
4. Spring Boot：自动配置、配置管理、项目结构规范（用 3.x 版本）
5. MyBatis / MyBatis-Plus：数据访问层
6. 权限认证：Spring Security 或 Sa-Token / JWT
7. 接口规范：RESTful 设计、参数校验、统一返回结构

**确定的学习资源**：
| 内容 | 资源 | 说明 |
|---|---|---|
| Spring 全家桶 | 黑马程序员《Spring + SpringMVC + SpringBoot + MyBatisPlus》B 站 | 免费、项目导向、国内最主流 |
| 备选（更细） | 尚硅谷雷丰阳《Spring Boot》B 站 | 免费，讲得深 |
| 官方文档（查漏） | [Spring Boot 官方文档](https://spring.io/projects/spring-boot) | 权威，遇到版本问题看它 |
| MyBatis | [MyBatis 中文文档](https://mybatis.org/mybatis-3/zh_CN/) | 免费 |
| 权限认证 | 尚硅谷 / 黑马《Spring Security》或 Sa-Token 官方文档 | 先会用，再懂原理 |

**检验标准**：独立搭一个 Spring Boot 项目，完成「登录注册 + 增删改查 + 分页 + 参数校验」的 REST API；能说清 IoC 和 AOP 是什么、Bean 生命周期。

---

## 第六阶段：工程化 + 中间件（6~8 周）

**目标**：具备真实项目里「能协作、能部署、能扛并发」的工程能力。

**学什么**：
1. Git 协作（分支管理、冲突解决、Code Review 习惯）
2. Linux 部署（常用命令、部署 Spring Boot、看日志、Nginx）
3. 消息队列：RabbitMQ 或 RocketMQ（选一个学透）
4. 微服务概念：注册中心（Nacos）、配置中心、网关（Spring Cloud Alibaba）
5. Docker 基础（容器化、镜像、Dockerfile、docker-compose）

**确定的学习资源**：
| 内容 | 资源 | 说明 |
|---|---|---|
| Linux + 部署 | 韩顺平《Linux》B 站 + 黑马《Linux 运维》 | 免费，边学边在虚拟机/云服务器操作 |
| 消息队列 | 尚硅谷《RabbitMQ》或《RocketMQ》B 站 | 免费，二选一 |
| 微服务 | 黑马程序员《Spring Cloud Alibaba》B 站 | 免费，国内企业主流 |
| Docker | 《Docker 技术入门与实战》或 B 站尚硅谷 Docker | 免费视频优先 |

**检验标准**：把自己第五阶段的项目部署到云服务器并用域名访问；用 Docker 跑通一个 MySQL + 应用；说清「消息队列解决了什么问题」。

---

## 第七阶段：数据结构与算法 + 计算机基础（贯穿全程）

**目标**：通过面试算法关，建立计算机底层认知（不追求竞赛难度）。

**学什么**：
- 数据结构：数组、链表、栈、队列、哈希表、树（二叉树/BST）、堆、图（了解）
- 算法：排序、二分、双指针、递归/回溯、动态规划入门、常见贪心
- 计算机基础：操作系统（进程/线程/内存/文件）、计算机网络（TCP/UDP、三次握手、HTTPS）

**确定的学习资源**：
| 内容 | 资源 | 说明 |
|---|---|---|
| 算法主课 | 《代码随想录》（[programmercarl.com](https://programmercarl.com/) 免费网站 + B 站视频） | 按专题刷，最适合面试，强烈推荐 |
| 刷题平台 | [LeetCode 中国](https://leetcode.cn/) | 按代码随想录顺序刷 |
| 算法书（可选） | 《labuladong 的算法笔记》 | 与代码随想录二选一 |
| 操作系统 | 《王道考研·操作系统》B 站 | 免费，讲得清楚 |
| 计算机网络 | 《图解 HTTP》+《图解 TCP/IP》或王道计算机网络 | 通俗优先 |

**节奏建议**：第二阶段起每周 2~3 次、每次 1 小时，先刷「数组、链表、哈希、字符串」等简单专题；面试前 2 个月集中冲刺高频题（Top 100）。

---

## 第八阶段：AI 基础认知（4~6 周）

> 这一阶段**不需要你写 AI 代码**，目的是建立正确认知，避免后面被各种名词绕晕。可与第六阶段并行。

**目标**：理解机器学习/深度学习/大模型「是什么、能做什么、边界在哪」，能看懂技术文章里的基本概念。

**学什么（由浅入深，按顺序）**：
1. AI 全景图：机器学习、深度学习、大模型（LLM）的关系
2. 神经网络直觉理解（无需深究数学推导）
3. Transformer 与注意力机制（懂「为什么会预测下一个词」即可）
4. 大模型能力：生成、理解、推理；什么是上下文、token、温度参数
5. 大模型局限：幻觉、知识时效、私有数据

**确定的学习资源**：
| 内容 | 资源 | 说明 |
|---|---|---|
| 科普/直觉理解 | 3Blue1Brown《神经网络》系列（B 站有中文字幕） | 免费、动画极佳 |
| 机器学习入门 | 吴恩达《Machine Learning Specialization》（Coursera，有中文字幕） | 权威，可免费旁听（audit） |
| 深度学习入门 | 李宏毅《机器学习》/《深度学习》B 站公开课 | 免费、中文、幽默好懂 |
| LLM 科普 | 吴恩达 DeepLearning.AI 短课《Generative AI for Everyone》 | 免费、短、建立全局观 |
| Transformer 直觉 | 3Blue1Brown 或 B 站搜「Transformer 通俗讲解」 | 能听懂注意力机制即可 |

**检验标准**：能用自己的话向别人解释「大模型是怎么生成文字的」「什么是 token」「为什么模型会一本正经地胡说」。

---

## 第九阶段：大模型应用开发（6~8 周）

> 这是「AI 模块」真正落地的核心。**作为后端开发，你的重点是「用 API + 工程手段」，而不是训练模型。**

**目标**：掌握大模型应用开发的四大核心能力，能独立搭建一个智能问答/知识库应用。

**学什么（按顺序）**：
1. 大模型 API 调用：OpenAI 兼容接口、DeepSeek / 通义千问 Qwen API
2. Prompt 工程：提示词设计、结构化输出、Few-shot
3. RAG（检索增强生成）：文档切分、向量化（Embedding）、向量数据库检索、召回重排
4. Function Calling / 工具调用：让模型调用你的后端接口
5. Agent（智能体）基础：多轮规划、工具编排、记忆
6. 向量数据库：选一个（如 Milvus / pgvector / Elasticsearch）

**确定的学习资源**：
| 内容 | 资源 | 说明 |
|---|---|---|
| Prompt 工程 | 吴恩达 DeepLearning.AI《ChatGPT Prompt Engineering for Developers》 | 免费、经典入门 |
| RAG | 吴恩达 DeepLearning.AI《Building and Evaluating Advanced RAG》 | 免费、进阶 |
| Function Calling | 吴恩达 DeepLearning.AI《Function Calling, Data Extraction》相关短课 | 免费 |
| Agent | 吴恩达 DeepLearning.AI《AI Agents》系列 | 免费 |
| DeepSeek 开发 | [DeepSeek 官方 API 文档](https://api-docs.deepseek.com/zh-cn/) | 中文、便宜、国内可直接用 |
| 通义千问 | [阿里云百炼 Qwen 文档](https://help.aliyun.com/zh/model-studio/) | 中文、生态全 |
| 向量数据库 | Milvus 官方文档 / [Milvus](https://milvus.io/) | 最主流，有中文文档 |

> 说明：吴恩达的这些短课代码多是 Python 写的，**你只需理解「原理和流程」**，代码实现放到第十阶段用 Java 重写——这正是后端开发的价值所在。

**检验标准**：用任意语言 + DeepSeek API 做一个「能回答你上传文档内容」的 RAG 问答 Demo（哪怕脚本简单，理解切分-向量化-检索-生成全流程即可）。

---

## 第十阶段：Java + AI 实战集成（6~8 周）

> 把上一阶段学的 AI 能力，用 Java 生态落地——这是你区别于「只会调 Python 脚本」的差异化竞争力。

**目标**：掌握 Spring AI 或 LangChain4j，把 RAG / 工具调用 / Agent 集成进 Spring Boot 后端。

**学什么**：
1. 框架选型：Spring AI（与 Spring 生态天然融合）vs LangChain4j（功能更全、更灵活）——**建议主学 Spring AI，LangChain4j 了解**，或二者都接触后选一个深入
2. Spring AI 核心：ChatClient、结构化输出、Embedding、VectorStore
3. 把 RAG 拆成后端服务：文档上传 → 切分 → 向量化入库 → 检索 → 组装 prompt → 调用模型
4. 工具调用（Tool/Function）：让模型调用你的业务 API
5. 流式输出（SSE）：实现打字机效果
6. 生产化：API Key 管理、限流、成本控制、异常兜底、可观测

**确定的学习资源**：
| 内容 | 资源 | 说明 |
|---|---|---|
| Spring AI 官方 | [Spring AI 官方文档](https://docs.spring.io/spring-ai/reference/) | 权威，跟着 quickstart 做 |
| LangChain4j 官方 | [LangChain4j 官方文档](https://docs.langchain4j.dev/) | 权威，示例丰富 |
| 中文视频 | B 站搜「Spring AI」「LangChain4j 实战」（黑马/尚硅谷/个人 up 均有） | 跟着敲，视频更新快 |
| 实战参考 | 阿里云开发者社区《构建基于 Java 的 AI 智能体：LangChain4j 与 Spring AI 实现 RAG》 | 中文博客，可参考思路 |
| 开源项目 | GitHub 搜 `spring-ai` / `langchain4j` 的 examples 仓库 | 直接看官方示例代码 |

**检验标准**：把第九阶段的 RAG Demo 用 **Spring Boot + Spring AI + Milvus/Redis** 完整重写成一个可部署的后端服务，支持文档上传、流式问答、工具调用。

---

## 第十一阶段：综合项目实战（8 周以上）

> 简历上真正有分量的是「项目」，不是「学过」。做 1~2 个有深度的项目，AI 模块是亮点。

**推荐项目方向（由易到难，任选做深）**：

1. **企业知识库智能问答系统**（最适合入门）
   - 技术栈：Spring Boot + MyBatis-Plus + Redis + MySQL + Spring AI + DeepSeek/Qwen + 向量库
   - 亮点：文档上传解析、RAG 检索、流式输出、多轮对话、权限管理

2. **智能客服 / 工单助手**
   - 亮点：Function Calling 调用业务接口查订单、Agent 多轮引导、人机协同（转人工）

3. **AI 代码 / 内容生成平台**
   - 亮点：模板 + Prompt 编排、多模型路由、计费与限流、结果评测

4. **RAG + Agent 的垂直行业应用**（结合你熟悉的领域，如医疗、电商、法律）

**资源**：
- B 站搜上述关键词 + 「实战项目」，有大量免费完整项目视频（黑马、尚硅谷、个人 up 主）
- 一定要**自己动手改需求、加功能**，不要照抄——面试官一眼能看出是抄的

**检验标准**：项目能完整跑通、部署上线、写清楚 README 和架构图；能讲出「为什么这么设计、遇到什么坑、怎么优化的」。

---

## 第十二阶段：求职准备（贯穿 + 最后 4 周冲刺）

**学什么**：
1. Java 后端八股文（集合、JVM、并发、MySQL、Redis、Spring、微服务）
2. AI 相关面试题（RAG 原理、向量检索、Prompt、Agent、幻觉应对、成本控制）
3. 简历打磨：突出「Java 后端 + AI 模块」的复合能力
4. 项目复盘：能 3 分钟讲清项目背景、架构、难点、成果

**确定的学习资源**：
| 内容 | 资源 | 说明 |
|---|---|---|
| 八股文 | 牛客网面经 + 微信公众号「JavaGuide」（[javaguide.cn](https://javaguide.cn/) 免费） | 系统全面 |
| AI 面试题 | 牛客/Boss 直聘搜「AI 应用开发 / 大模型应用」面经 | 针对性准备 |
| 模拟面试 | 牛客网模拟面试、AI 模拟面试工具 | 练表达 |

---

## 附：全阶段资源速查表（收藏用）

| 类别 | 首选资源 | 费用 | 地址/平台 |
|---|---|---|---|
| Java 基础视频 | 韩顺平《零基础学 Java》 | 免费 | B 站 |
| Java 基础视频 | 黑马程序员《Java 基础》 | 免费 | B 站 |
| Java 文字教程 | 廖雪峰 Java 教程 | 免费 | liaoxuefeng.com |
| JVM | 《深入理解 Java 虚拟机》周志明 | 付费书 | 各大书店/微信读书 |
| 并发 | 《Java 并发编程的艺术》 | 付费书 | 各大书店 |
| MySQL | 尚硅谷 MySQL +《MySQL 实战 45 讲》 | 视频免费/专栏付费 | B 站 / 极客时间 |
| Redis | 尚硅谷 Redis | 免费 | B 站 |
| Spring 全家桶 | 黑马程序员 Spring 系列 | 免费 | B 站 |
| 微服务 | 黑马《Spring Cloud Alibaba》 | 免费 | B 站 |
| 算法 | 代码随想录 | 免费 | programmercarl.com + B 站 |
| 计算机网络 | 《图解 HTTP》+ 王道 | 书付费/视频免费 | 书店 / B 站 |
| 操作系统 | 王道考研操作系统 | 免费 | B 站 |
| ML 入门 | 吴恩达 Machine Learning Specialization | 免费旁听 | Coursera |
| 深度学习 | 李宏毅机器学习/深度学习 | 免费 | B 站 |
| LLM 应用 | 吴恩达 DeepLearning.AI 短课系列 | 免费 | deeplearning.ai |
| 大模型 API | DeepSeek / 通义千问 Qwen | 按量付费（便宜） | 官方文档 |
| Java AI 框架 | Spring AI / LangChain4j | 免费 | 官方文档 + B 站 |
| 向量数据库 | Milvus | 免费开源 | milvus.io |
| 八股文 | JavaGuide | 免费 | javaguide.cn |

---

## 给你的几点实在建议（避坑）

1. **顺序比速度重要**：前五个阶段（Java 基础到 Spring）一定打牢，这是后端的地基，AI 是建在上面的楼层。基础没打好就冲 AI，容易两头空。
2. **AI 部分走「应用工程」路线，不要碰模型训练**：你学的是「怎么把现成大模型接进业务」，数学够用就行，别陷入公式推导。
3. **框架二选一深入**：Spring AI 和 LangChain4j 学一个吃透即可，另一个知道「能干什么」就够，面试和工作中再切换成本很低。
4. **项目一定要自己动手**：看 10 个视频不如自己完整做 1 个项目。哪怕做得粗糙，也要能讲清楚每一步为什么。
5. **GitHub/Gitee 是你的第二份简历**：每个阶段的小项目都推上去，面试官很看重。
6. **学习用 AI 工具本身**：遇到不会的，直接用 DeepSeek/ChatGPT 提问、让它讲解代码，这也是在练习你未来要开发的「AI 模块」的用法。
7. **版本选择**：Java 学 **17 或 21 LTS**（公司主流），Spring Boot 学 **3.x**；AI 相关用当前最新稳定版即可。

---

*路线图生成时间：2026 年。大模型/AI 生态更新很快，学 AI 部分时优先以官方文档为准。*