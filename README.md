# JavaScript Monopoly
JavaScript大富翁，复刻了童年与小伙伴玩的经典大富翁游戏。

在线试玩：https://seanboy.club/game/monopoly



## 思路

### HTML & CSS

- 配置选项框：选择金钱、玩家人数、电脑人数
- 选择角色框：选择角色
- 主地图：通过grid布局实现，通过JS动态添加棋格；中间的超大格子用来存放各种游戏信息，从上到下依次为：当前玩家、游戏选项、掷骰子区、玩家信息区。
- 各种组件：角色棋子、房子、升级房子的动画、购买框、消息框、地产信息卡片。

### 开始(initializing.js)

- 选择人数
- 选择角色
- 游戏开局

### 进行时(monopoly.js)

#### 主线

- 掷骰子
- 角色根据骰子点数setInterval移动
- setTimeout停下后触发棋格事件
- 事件完成后轮到下一个玩家

#### 其他

- 处理买地和升级地产
- 判断玩家顺序（避开停止和破产状态）
- 判断玩家破产
- 判断游戏结束

### 数据(data.js)

- 角色棋子
  - 名字
  - 金钱
  - 状态（活跃或破产）
  - 停止（代表天数，默认为0）
  - 是否玩家控制
  - 对应DOM节点
  - 当前在棋格位置
- 棋格
  - 地名
  - 地价
  - 状态（对应普通地产的等级或特殊区域）
  - 对应DOM节点
- 机会命运
  - 说明文字
  - 金钱数值
  - 是否停止

### DOM操作(dom-binding.js)

- 实现所有界面内容显示相关内容



## 花絮

- 这个大富翁是19年10月11日开始制作的，那时刚学JavaScript才半个月。最终花了7天左右时间做出了完整，无bug，游戏性强的版本（共两千多行代码）。
- 半年后，20年4月7日晚上，打算往前端方向发展求职之后，从现在的视角用原生JS重制了一遍，把多达一千五百行的JS代码缩到了仅六百多行，并新增了不少功能。
- 下一步将结合Vue框架来重制，很是期待现代化框架的功力能帮助我省多少功夫。