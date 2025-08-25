# 第一部分：组合逻辑回顾 (Combinational Logic)

## 1. 定义与核心概念 (Definition & Core Concepts)

- **组合逻辑电路 (Combinational Logic Circuit)**  
  - **定义 (Definition)**：输出只依赖于 **当前输入 (current inputs)**，没有 **记忆 (memory/state)** 功能。  
  - **特性 (Characteristics)**：  
    - **相同输入 → 相同输出** (Deterministic mapping)。  
    - 与输入历史无关。  
  - **区别 (Comparison)**：  
    - **组合逻辑 (Combinational)**：纯逻辑门 (logic gates only)，无触发器 (no flip-flops)。  
    - **时序逻辑 (Sequential)**：包含触发器/寄存器 (flip-flops/registers)，输出依赖于 **输入 + 状态 (state)**。

---

## 2. 设计与建模流程 (Design & Modeling Process)

1. **功能规格 (Specification)**：定义输入/输出和逻辑功能。  
2. **真值表 (Truth Table)**：列出所有输入组合与目标输出。  
3. **布尔表达式 (Boolean Expressions)**：  
   - **积之和 SOP (Sum of Products)**：最小项 (minterm) 相加。  
   - **和之积 POS (Product of Sums)**：最大项 (maxterm) 相乘。  
4. **化简 (Simplification)**：  
   - **代数化简 Boolean Algebra simplification**  
   - **卡诺图 Karnaugh Map (K-map)**  
   - **奎因–麦克拉斯基 Quine-McCluskey** 算法  
5. **电路实现 (Circuit Implementation)**：  
   - 基本逻辑门 (AND, OR, NOT, NAND, NOR, XOR, XNOR)。  
   - 可编程逻辑器件 (PLD, Programmable Logic Device)。  

---

## 3. 常见组合逻辑器件 (Common Combinational Circuits)

### 3.1 加法器 (Adders)
- **半加器 (Half Adder)**  
  - 输入：A, B  
  - 输出：和 Sum = A ⊕ B；进位 Carry = A·B  

- **全加器 (Full Adder)**  
  - 输入：A, B, Cin (进位输入)  
  - 输出：和 Sum = A ⊕ B ⊕ Cin；进位输出 Cout = AB + Cin(A ⊕ B)  

- **多位加法器 (Ripple-Carry Adder)**  
  - 由多个全加器级联。  
  - 缺点：进位延迟 (Carry propagation delay)。  

---

### 3.2 加减器 (Adder/Subtractor)
- 使用二进制补码 (Two’s complement) 实现减法。  
- 控制信号 M：  
  - M = 0 → 加法  
  - M = 1 → 减法（B 取反加 1）。  

---

### 3.3 多路选择器 (Multiplexer, MUX)
- 定义：从多个输入中选择一个输出。  
- **n:1 MUX**：n 个输入，log₂(n) 个选择信号 (select lines)，1 个输出。  
- 例：4:1 MUX → 需要 2 个选择信号 S0, S1。  

---

### 3.4 译码器 (Decoder)
- 定义：将二进制输入转化为唯一激活的输出。  
- **n:2ⁿ Decoder**：n 位输入 → 2ⁿ 个输出。  
- 应用：地址选择 (memory addressing)、指令译码。  

---

### 3.5 编码器 (Encoder)
- 定义：与译码器相反，将激活的输入转为二进制编码输出。  
- **优先编码器 (Priority Encoder)**：多个输入同时为 1 时，输出优先级最高的编码。  

---

### 3.6 比较器 (Comparator)
- 定义：比较两个二进制数的大小。  
- 输出：A > B、A = B、A < B。  

---

## 4. 实验与调试建议 (Lab & Debugging Tips)

- **电路绘制 (Schematic Drawing)**：保持电路清晰整洁。  
- **实验平台**：  
  - Logisim (仿真 simulation)  
  - 面包板 breadboard (实际搭建)。  
- **调试技巧 (Debugging)**：  
  - 检查电源/地 (VCC/GND)。  
  - 使用逻辑探针 (Logic Probe) 逐级检查。  
  - 遇到问题要系统化排查，而不是随意修改。  

---

## 5. 局限性 (Limitations)

- 无法存储历史状态 (no memory)。  
- 易受信号延迟和毛刺 (glitches) 影响。  
- 无法实现需要记忆的电路（如计数器、寄存器）。  
- → 需要 **时序逻辑 (Sequential Circuits)** 来补充。  

---

## 📌 小结 (Key Takeaways)

1. **组合逻辑 = 无记忆 (stateless)**。  
2. **设计流程**：规格 → 真值表 → 布尔表达式 → 化简 → 电路实现。  
3. **典型器件**：加法器、加减器、多路选择器、译码器、编码器、比较器。  
4. **实验建议**：电路整洁、逻辑探针调试、逐步排错。  

# 第二部分：时序逻辑与存储 (Sequential Logic & Memory)

> 目标：系统掌握 **时序电路 (Sequential Circuits)** 的核心概念、**D 触发器 (D Flip‑Flop)** 的工作机理与特性表、**锁存器 (Latch)** 与触发器的区别、**寄存器 (Register)** 与 **移位寄存器 (Shift Register)** 的类型与应用；补充工程级要点（**建立/保持时间 setup/hold**、**亚稳态 metastability**、**去抖动 debouncing**、**时钟域交叉 CDC** 等）。  
> 重要术语同时标注 **英文**（加粗），以便双语记忆与检索。

---

## 1. 组合逻辑 vs. 时序逻辑 (Combinational vs. Sequential)

- **组合逻辑 (Combinational Logic)**：仅由**逻辑门 (logic gates)** 构成；**输出只由当前输入决定**，同样输入总得到同样输出（无状态）。:contentReference[oaicite:0]{index=0}  
- **时序逻辑 (Sequential Logic)**：包含**触发器 (flip‑flops)** 等存储元件；**输出由当前输入 + 当前状态 (state)** 决定；**状态**在**时钟边沿 (clock edges)** 才更新（**同步时序 synchronous**）。:contentReference[oaicite:1]{index=1}  
- **状态/下一状态 (Present/Next State)**：当前状态与输入共同决定下一状态与输出。:contentReference[oaicite:2]{index=2}  
- **同步时序电路 (Synchronous Sequential Circuit)**：所有触发器共享**同一时钟 (common clock)**；存储元件**仅在边沿改变**，对比组合逻辑的“输入一变就变”。:contentReference[oaicite:3]{index=3}

---

## 2. D 触发器 (D Flip‑Flop) —— 核心存储单元

### 2.1 定义与基本行为 (Definition & Behavior)
- **接口**：**D（数据 data）**、**CLK（时钟 clock）**、**Q（输出）**。  
- **边沿触发 (edge‑triggered)**：在**上升沿 rising edge, 0→1** 时，**Q ← D** 并**保持**到下一个时钟边沿（期间不响应 D 的变化）。:contentReference[oaicite:4]{index=4} :contentReference[oaicite:5]{index=5}  
- **特性表 (Characteristic Table)**（“下一个时钟边沿后的输出”）：  
  | D | Q(t+1) | 含义 |
  |---|--------|------|
  | 0 | 0      | 下个上升沿后清零 |
  | 1 | 1      | 下个上升沿后置一 |  
  （课件“Characteristic Tables”）:contentReference[oaicite:6]{index=6}

### 2.2 符号与“边沿”标识 (Schematic Symbols)
- **三角形**表示**边沿触发 (edge‑triggered FF)**；常见为**上升沿**与**下降沿**两个版本。:contentReference[oaicite:7]{index=7}

### 2.3 实际器件与异步控制 (Real Devices & Async Controls)
- **异步置位/清零 (asynchronous SET/CLR 或 PRE/CLR)**：可在**非时钟边沿**直接**置 1/清 0** 输出；课程强调 **SET/CLR 常为低有效 (active‑low)**。:contentReference[oaicite:8]{index=8}  
- **常用芯片**：  
  - **74HCT74**（双 D 触发器 Dual D‑FF）  
  - **74HCT273**（8×D‑FF，可存 1 Byte）:contentReference[oaicite:9]{index=9}

### 2.4 时序波形与“只在边沿改变”的考题点
- 波形题通常考**Q 仅在 CLK 上升沿**采样 D；在**边沿间隔**，即使 D 抖动，Q 也**不变**。:contentReference[oaicite:10]{index=10}  
- 对**负边沿 (falling edge)** 的 D‑FF：只有**下降沿**采样；“CLK=0 时 D 改变是否影响 Q？”是常见判断陷阱（答案：**不影响**，等到下降沿）。此类判断在 Lab05 选择题中出现。:contentReference[oaicite:11]{index=11}

---

## 3. 锁存器 vs. 触发器 (Latch vs. Flip‑Flop)

- **锁存器 Latch**：**电平敏感 (level‑sensitive)**；输入电平变化立即能影响输出。  
- **触发器 Flip‑Flop**：**边沿敏感 (edge‑triggered)**；只在**时钟边沿**改变。:contentReference[oaicite:12]{index=12}  
- **SR 锁存器 (S‑R Latch)**：  
  - **NOR 交叉耦合**形式：S=1 置位、R=1 复位；S=R=1 禁止。课件要求补全真值表与推理。:contentReference[oaicite:13]{index=13}  
  - **NAND 交叉耦合**形式：作为作业要求进行分析与真值表补全。:contentReference[oaicite:14]{index=14}  
- **课程聚焦**：仅深入 **D 触发器**；**JK/T FF**不作展开。:contentReference[oaicite:15]{index=15}

---

## 4. 寄存器 (Registers)

- **定义**：由 **n 个 D‑FF** 组成的**n 位寄存器**，可存 n 位二进制数；**纯时序**（不含组合逻辑）。:contentReference[oaicite:16]{index=16}  
- **用途**：处理器中存储**数据/指令 (data/instructions)**；是**流水线/状态机**的基本单元。:contentReference[oaicite:17]{index=17}

---

## 5. 移位寄存器 (Shift Registers)

### 5.1 定义与作用
- **定义**：能在时钟作用下将寄存的信息按位**左移/右移 (shift left/right)** 的寄存器。:contentReference[oaicite:18]{index=18}  
- **应用**：  
  - **串/并转换 (Serial ⇄ Parallel conversion)**：SISO/SIPO/PISO/PIPO。:contentReference[oaicite:19]{index=19}  
  - **延迟/队列**、简单流水线。:contentReference[oaicite:20]{index=20}

### 5.2 类型（按 I/O 方式）
- **SISO**（Serial‑In Serial‑Out，串入串出）  
- **SIPO**（Serial‑In Parallel‑Out，串入并出）  
- **PISO**（Parallel‑In Serial‑Out，并入串出）  
- **PIPO**（Parallel‑In Parallel‑Out，并入并出）

### 5.3 模式与结构拓展
- **并行装载 + 串行移位 (Parallel Load + Serial Shift)**：课件示意需课堂补全。:contentReference[oaicite:21]{index=21}  
- **双向移位寄存器 (Bidirectional Shift Register)**：用**多路选择器 (MUX)** 选择左/右移（**DIRN=0 左移，DIRN=1 右移**）。:contentReference[oaicite:22]{index=22}  
- **通用移位寄存器 (Universal Shift Register)**：支持**并入/并出/串移**等模式，功能最强（两页结构图）。:contentReference[oaicite:23]{index=23}  
- **8 位宽 4 级移位队列**：多个 8 位寄存器级联，带**ENB 使能**与统一时钟；可实现“一拍前推”。:contentReference[oaicite:24]{index=24}

---

## 6. 工程级时序要点 (Timing in Practice)

> 以下为课程强调之外的工程常识，**强烈建议掌握**，以保证电路稳定与可测。

### 6.1 建立/保持时间 (Setup/Hold Time)
- **建立时间 t_setup**：**时钟边沿之前**，**D 必须保持稳定**的最短时间。  
- **保持时间 t_hold**：**时钟边沿之后**，**D 仍需保持稳定**的最短时间。  
- 违反会导致**亚稳态 (metastability)** 或**错误采样**。

**基本时序约束（相邻寄存器）**：
- **时钟周期**：`Tclk ≥ t_CQ(max) + t_pd_comb(max) + t_setup + t_skew`  
- **保持约束**：`t_CQ(min) + t_pd_comb(min) − t_skew ≥ t_hold`

> 含义：前级寄存器的 **时钟到输出延迟 t_CQ (Clock‑to‑Q)** + 组合逻辑最大延迟 + 建立时间 + 时钟偏斜（最坏情况）不得超过时钟周期；同时组合路径的**最小延迟**要足以满足保持时间。

### 6.2 亚稳态 (Metastability) 与时钟域交叉 (CDC)
- **亚稳态**：D 违反 setup/hold 时，Q 可能在短时内不确定。  
- **CDC**：跨不同时钟域传输信号必须用**双触发器同步**（single‑bit）或**异步 FIFO/握手**（multi‑bit），避免亚稳态扩散。

### 6.3 复位策略 (Reset Strategy)
- **异步复位 (async reset)**：**低有效**常见；**释放时**最好**与时钟同步**（“异步断言、同步释放”）以避免不一致状态。  
- **同步复位 (sync reset)**：用时钟边沿采样复位，更易收敛时序（但需要时钟）。

### 6.4 机械按键去抖 (Button Debouncing)
- **PRE/CLR/CLK** 若接**机械按钮**，必须**去抖**（RC + 施密特/数字滤波），否则一次按压会产生**多次触发**。  
- Lab05 提示：**PRE/CLR 与按钮之间可加反相器**（常见为**低有效**），同时便于整形波形。:contentReference[oaicite:25]{index=25}

---

## 7. 实验落地 (Labs) —— 搭建与调试清单

- **Lab04**：组合电路搭建流程：**先画图** → **定真值表** → **仿真/上板** → **系统化测试**；优先检查 **VCC/GND**，用**逻辑探针**由输入向输出排查。:contentReference[oaicite:26]{index=26} :contentReference[oaicite:27]{index=27}  
- **Lab05**（重点在 D‑FF）任务：  
  1) 2 输入 **NOR**；2) **RS‑Latch（交叉 NOR）**；3) **D‑FF** 电路（**74HCT74**，**按钮接 CLK/PRE/CLR**，**拨码开关接 A/B**，**LED 显示 Q/Q’**；考虑 **PRE/CLR 低有效**与**按钮去抖/反相**）。:contentReference[oaicite:28]{index=28} :contentReference[oaicite:29]{index=29}

---

## 8. 易错点与速记 (Pitfalls & Cheat‑Sheet)

- **D‑FF 只在边沿采样**；**非边沿**期间 Q 不变。波形题抓“采样瞬间”。:contentReference[oaicite:30]{index=30}  
- **寄存器 = n×D‑FF**，**无组合逻辑**；不要把“寄存器”与“移位寄存器”混淆（后者 = 寄存器 + 受控位移）。:contentReference[oaicite:31]{index=31} :contentReference[oaicite:32]{index=32}  
- **计数器 Counter** 属于**时序电路**（非组合），是常见选择题陷阱。:contentReference[oaicite:33]{index=33}  
- **PRE/CLR 多为低有效**；按钮不去抖会“乱跳”。:contentReference[oaicite:34]{index=34} :contentReference[oaicite:35]{index=35}

---

## 9. 术语对照 (Keywords • 中英对照)

- **时序电路** Sequential Circuit  
- **组合电路** Combinational Circuit  
- **触发器** Flip‑Flop（本课聚焦 **D‑FF**）  
- **锁存器** Latch（**电平敏感 level‑sensitive**）  
- **上/下升沿** Rising/Falling Edge  
- **预置/清零** Preset/Clear（**PRE/CLR，常低有效 active‑low**）  
- **寄存器** Register（**n×D‑FF**）  
- **移位寄存器** Shift Register（SISO/SIPO/PISO/PIPO，**Bidirectional/Universal**）  
- **建立/保持时间** Setup/Hold Time  
- **时钟到输出** Clock‑to‑Q (t_CQ)  
- **亚稳态** Metastability  
- **时钟域交叉** Clock Domain Crossing (CDC)  
- **去抖动** Debouncing  
- **时钟偏斜** Clock Skew  
- **最大/最小路径延迟** Max/Min Path Delay

---

## 10. 练习与自测 (Quick Checks)

1) 画出一个 **负边沿触发** D‑FF 的 Q 波形（给定 D、CLK）；指出**哪些时刻采样**。  
2) 设计一个 **3 位双向移位寄存器**（DIRN=0 左移，1 右移）：画出由 **MUX + D‑FF** 组成的结构框图。:contentReference[oaicite:36]{index=36}  
3) 给定两级寄存器的组合逻辑延迟范围 `[t_pd_min, t_pd_max]`，验证是否满足上面的 **时序约束**。  
4) 解释为什么 **按钮直接接 CLK** 会导致**不可靠触发**；给出**去抖**与**整形**方案。:contentReference[oaicite:37]{index=37}

---

### 参考 (Slides Used)
- Lec05：**Flip‑flops**（D‑FF 定义、特性表、SR Latch、符号/器件、Latch vs FF）:contentReference[oaicite:38]{index=38} :contentReference[oaicite:39]{index=39} :contentReference[oaicite:40]{index=40}  
- Lec06：**Sequential Circuits 1 – Shift Registers**（同步时序、寄存器、移位寄存器、通用/双向/并装串移）:contentReference[oaicite:41]{index=41} :contentReference[oaicite:42]{index=42} :contentReference[oaicite:43]{index=43}  
- Lab04/Lab05：**实验流程、D‑FF 电路搭建、调试提示**:contentReference[oaicite:44]{index=44} :contentReference[oaicite:45]{index=45}


# 第三部分：移位寄存器与扩展 (Shift Registers & Extensions)

> 本部分在前两节 **组合逻辑** 与 **基础时序逻辑 (D Flip-Flop, 寄存器)** 的基础上，进一步深入 **移位寄存器 (Shift Registers)**。  
> 重点内容：移位寄存器的种类、结构、功能、典型应用、工程细节（时序约束、串并转换）、以及拓展知识（流水线、硬件实现方式、实际芯片等）。

---

## 1. 移位寄存器的定义与本质 (Definition & Essence)

- **移位寄存器 (Shift Register)**：  
  由 **一组 D 触发器 (D Flip-Flops)** 组成，并通过**受控连线**在时钟作用下将存储的二进制信息**逐位移动 (shift)**。  
- **核心思想**：在**每个时钟边沿**，所有触发器的值**同步更新**，按照连线方向**整体平移一位**。  
- **方向**：可分为 **左移 (shift left)**、**右移 (shift right)**，有些支持**双向移位 (bidirectional)**。  
- **扩展模式**：加入控制逻辑可实现 **串/并输入输出转换 (serial ⇄ parallel conversion)**。

---

## 2. 移位寄存器的分类 (Types of Shift Registers)

### 2.1 按输入输出方式分类
1. **SISO (Serial-In Serial-Out, 串入串出)**  
   - 数据从串行输入端逐位移入，按顺序在串行输出端移出。  
   - 常用于**数据延迟**或**串行缓冲**。  

2. **SIPO (Serial-In Parallel-Out, 串入并出)**  
   - 串行输入进入触发器，若干时钟后，可在各触发器的 Q 输出端一次性读出。  
   - 用途：**串行通信接收端**，如 UART 串口数据接收。  

3. **PISO (Parallel-In Serial-Out, 并入串出)**  
   - 并行数据同时加载到寄存器中，再逐位移出。  
   - 用途：**串行通信发送端**，将并行数据转为串行输出。  

4. **PIPO (Parallel-In Parallel-Out, 并入并出)**  
   - 输入/输出均为并行；相当于普通寄存器，但可以控制移位。  

---

### 2.2 按移位方向分类
- **单向移位 (Unidirectional Shift)**：只能向左或向右移。  
- **双向移位 (Bidirectional Shift)**：可根据控制信号 **DIRN (Direction)** 选择左移或右移。  
  - **DIRN=0 → 左移**，**DIRN=1 → 右移**。  
  - 常用**多路选择器 (MUX)** 实现方向切换。  

---

### 2.3 通用移位寄存器 (Universal Shift Register)
- **功能最全**，支持：  
  - 并行输入/并行输出 (Parallel load/output)  
  - 串行输入/串行输出 (Serial shift)  
  - 左移/右移方向选择  
- 硬件上通过**选择器 (MUX)** 控制输入路径，实现不同模式切换。  
- 是移位寄存器家族中最灵活的，广泛应用于复杂数据通道。  

---

## 3. 移位寄存器的典型应用 (Applications)

1. **串行与并行转换 (Serial ⇄ Parallel conversion)**  
   - 串行接收数据 → SIPO  
   - 并行数据发送 → PISO  
   - 常见于**UART、SPI、I²C** 等通信接口。  

2. **数据存储与延迟线 (Data Delay Line)**  
   - SISO 可作为延迟单元，使输入信号在若干时钟后输出。  
   - 在 **数字滤波器 (FIR filters)** 中常用于实现抽头延迟线 (tap delay line)。  

3. **队列与流水线 (Queues & Pipelines)**  
   - 多级移位寄存器可实现**数据流动的队列**，用于图像处理流水线或并行处理单元。  

4. **伪随机数生成 (Pseudo Random Number Generation)**  
   - **线性反馈移位寄存器 (LFSR, Linear Feedback Shift Register)** 利用移位寄存器 + 异或反馈生成伪随机序列。  
   - 应用：加密、误码检测 (CRC)、数字通信中的扩频。  

5. **状态机 (Finite State Machines)**  
   - 移位寄存器可作为 FSM 的状态寄存器，每个时钟按规则更新。  

---

## 4. 电路实现 (Circuit Implementation)

### 4.1 基本结构（以 SISO 为例）
- n 个 D-FF 串联：  
  - 第一个触发器 D 端接输入 Din；  
  - 每级的 Q 接到下一级 D；  
  - 最后一位 Qn 为输出。  
- 在每个时钟边沿，数据整体右移一位。  

### 4.2 双向移位寄存器的实现
- 使用 **2:1 MUX** 作为每级 D-FF 的输入选择：  
  - **DIRN=0 → 来自左侧 Q**  
  - **DIRN=1 → 来自右侧 Q**  

### 4.3 通用移位寄存器的实现
- 每级 D-FF 的输入端用 **4:1 MUX** 选择：  
  1. 串行左移  
  2. 串行右移  
  3. 并行加载  
  4. 保持当前值  

---

## 5. 工程与时序分析 (Engineering & Timing)

- **同步更新**：所有触发器在时钟边沿同时更新，避免组合逻辑带来的毛刺。  
- **时序要求**：必须满足 **setup/hold 时间** 和 **Clock-to-Q 延时**，保证数据在移位时正确采样。  
- **级联延迟**：长移位寄存器需考虑**全链路时延**，在高频时钟下可能需插入流水线。  

---

## 6. 扩展知识 (Extended Knowledge)

### 6.1 LFSR (Linear Feedback Shift Register)
- 一种特殊的移位寄存器，增加了**异或反馈逻辑**。  
- 可生成**伪随机数序列 (Pseudo Random Sequence)**。  
- 应用：CRC 校验、伪随机测试向量、通信中的扩频。  

### 6.2 硬件实例
- **74HC595**：常用的 **SIPO** 移位寄存器，带有锁存输出，可驱动 LED 数码管。  
- **74HC165**：常用的 **PISO** 移位寄存器，用于键盘矩阵输入扫描。  

### 6.3 与处理器关系
- CPU 内部的**流水线寄存器**本质上就是移位寄存器。  
- **指令流水线 (Instruction pipeline)**：通过寄存器分级传递数据，使得 CPU 在每个时钟周期处理不同阶段的指令。  

---

## 7. 小结 (Summary)

1. **移位寄存器 = 寄存器 + 数据移动能力**。  
2. 分类：SISO / SIPO / PISO / PIPO；单向 / 双向 / 通用。  
3. 典型应用：串并转换、延迟线、队列、LFSR、通信接口。  
4. 工程要点：同步更新、setup/hold 要求、长链需流水线。  
5. 扩展：LFSR 在通信与加密领域广泛应用；74HC595/165 是常用的移位寄存器芯片。  

---

