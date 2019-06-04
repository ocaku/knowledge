## 寄存器英文缩写

AH&AL＝AX(accumulator)：累加寄存器    
BH&BL＝BX(base)：基址寄存器    
CH&CL＝CX(count)：计数寄存器    
DH&DL＝DX(data)：数据寄存器    
SP（Stack Pointer）：堆栈指针寄存器    
BP（Base Pointer）：基址指针寄存器    
SI（Source Index）：源变址寄存器    
DI（Destination Index）：目的变址寄存器    
IP（Instruction Pointer）：指令指针寄存器    
CS（Code Segment）代码段寄存器   
DS（Data Segment）：数据段寄存器   
SS（Stack Segment）：堆栈段寄存器   
ES（Extra Segment）：附加段寄存器   
OF overflow flag 溢出标志 操作数超出机器能表示的范围表示溢出,溢出时为1.   
SF sign Flag 符号标志 记录运算结果的符号,结果负时为1.   
ZF zero flag 零标志 运算结果等于0时为1,否则为0.   
CF carry flag 进位标志 最高有效位产生进位时为1,否则为0.   
AF auxiliary carry flag 辅助进位标志 运算时,第3位向第4位产生进位时为1,否则为0.   
PF parity flag 奇偶标志 运算结果操作数位为1的个数为偶数个时为1,否则为0.   
DF direcion flag 方向标志 用于串处理.DF=1时,每次操作后使SI和DI减小.DF=0时则增大.   
IF interrupt flag 中断标志 IF=1时,允许CPU响应可屏蔽中断,否则关闭中断.   
TF trap flag 陷阱标志 用于调试单步操作.   
 
