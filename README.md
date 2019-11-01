- # 数据结构

  ## 1. 数据结构绪论

  ### 1.1 什么是数据结构？

  - 数据结构是数据对象，以及存在于该对象的实例和组成实例的数据元素之间的各种联系，这些联系可以通过定义相关的函数来定义  《数据结构、算法与应用》

  > 数据结构是一门研究非数值计算的程序设计问题中的操作对象，以及他们之间的关系和操作等相关问题学科
  >
  > 程序设计 = 数据结构 (问题的数学模型)+ 算法(处理问题的策略)
  >
  > 数据结构描述现实世界实体的数学模型（非数值运算）机器上的操作在计算机中的表示何实现
  >
  > 数据结构是带结构的数据集合

  

  ### 1.2 基本概念和术语

  - 数据

  > 描述客观事物的符号，是计算机中可以操作的对象，是能被计算机识别，并输入给计算机处理的符号集合
  >
  > 符号（前提）：1.可以输入到计算机中  2.能被计算机程序处理

  - 数据元素

  > 是组成数据的、有一定意义的基本单位，在计算机中通常作为整体处理。也成为记录

  - 数据项

  > 一个元素可以有若干个数据项组成
  >
  > 数据项是数据不可分割的最小单位

  - 数据对象

  > 是性质相同的数据元素的集合，是数据的子集

  - 数据结构

  > 是相互之间存在一种或多种特定关系的**数据元素集合**

  ### 1.3 逻辑结构与物理结构

  #### 1.3.1 逻辑结构

  - 数据结构形式化定义为：

  > 数据结构是一个二元数组 DATA_SOURCES = (D,S)
  >
  > D是数据元素的有限集，S是D上关系的有限集

  - 是指数据对象中数据元素之间的相互关系

  ##### 1.3.1.1集合结构

  ​          集合结构除了同属一个结构外，他们之间没有其他关系

  ##### 1.3.1.2 线性结构

  ​          线性结构中数据元素之间是 一对一的关系

  ##### 1.3.1.3 树形结构

  ​          数据元素之间存在一种一对多的层次关系

  ##### 1.3.1.4 图形结构

  ​          数据元素是多对多

  #### 1.3.2 物理结构

  - 数据的逻辑结构在计算机中存储的形式（逻辑结构在存储器中的映像）

  ##### 1.3.2.1 顺序存储结构

  ​        把数据元素存放在地址连续的存储单元里，其数据间的逻辑关系和物理关系是一致的

  ##### 1.3.2.2 链式存储结构

  ​        以附加信息（指针）表示后继关系

  ​        是把数据元素存放在任意的存储单元里，这组存储单元可以是连续的，也可以是不连续的

  #### 1.4 抽象数据类型

  - 数据类型： 是指一组性质相同的值的集合及定义在此集合上的一些操作的总称

  在使用高级程序语言编写的程序中，必须对程序中出现的每一个变量、常量或表达式，明确说明他们所属的数据类型

  > 在C语言中按照取值不同，数据类型可以分为两类：
  >
  > - 原子类型：是不可以在分解的基本类型，包括整形、实型，字符型
  > - 结构类型：由若干个类型组成而成，是可以再分解的。例如 整形数组

  - 抽象 是指抽取出事物具有普遍性的性质
  - 抽象数据类型

  > 抽象数据类型（Abstract Data Type，ADT ）：是指一个数学模型（数据结构中的数据结构）及定义在该模型上的一组操作
  >
  > ADT：有两个重要特性：
  >
  > - 数据抽象：用ADT描述程序处理的实体时，强调的是其本质的特征、其所能完成的功能以及他和外部用户的接口（即外界使用他的方法）
  >
  > 例如：抽像数据类型复数定义：
  >
  > ​    ADT Complex{
  >
  > ​      数据对象：
  >
  > ​             D = {e1,e2 | e1,e2 属于RealSet}
  >
  > ​       数据关系：
  >
  > ​             R1 =  {<e1,e2>|e1是复数的实数部分，e2是复数的虚数部分}
  >
  > ​        基本操作：
  >
  > ​              InitComplex（&Z，v1,v2）
  >
  > ​              操作结果：构造复数Z，其实部与虚部分别赋值以v1和v2的值
  >
  > ​              DestroyComplex（&Z）
  >
  > ​             操作结果：复数Z被销毁
  >
  > ​             GetReal（Z,&realPart）
  >
  > ​              初始条件：复数已存在
  >
  > ​              操作结果：用 realPart 返回复数Z的实部值
  >
  > ​              GetImag(Z,&imagPart)
  >
  > ​               初始条件：复数已存在
  >
  > ​               操作结果：用ImagPart返回复数Z的虚部
  >
  > ​              Add（z1，z2，&sum）
  >
  > ​              初始条件：z1,z2是复数
  >
  > ​               操作结果：用sum返回两个复数的z1,z2的和
  >
  > 
  >
  > } ADT  Complex
  >
  > - 数据封装：将尸体的外部特性和其内部实现细节分离，并且对外部用户隐藏其内部实现细节
  >
  > 抽象数据类型的描述方法：
  >
  > ​    抽象数据类型可用（D，S , P）三元组表示
  >
  > 其中，D是数据对象，
  >
  > ​           S是D上的关系级，
  >
  > ​           P是对D的基本操作集
  >
  > - 抽象数据类型的表示和实现
  >
  > 抽象数据类型需要通过固有数据类型
  >
  > 

  

  ## 2. 算法

  - 算法是解决特定问题求解步骤的描述，在计算机中表现为指令的有限序列，并且每条指令表示一个或多个操作
  - 算法是为了解决某类问题 而规定的一个有限长的操作序列

  ### 2.1 算法的五大特性

  - 输入输出： 具有零个或多个输入。至少由一个或多个输出
  - 有穷性：在算法执行有限个步骤后，自动结束而不会无限循环  1.算法执行有限步就结束 2.每一个指令每一步执行的时间都是有限的（合理的）
  - 确定性：算法的每一个步骤都有确定的含义，不会出现二义性   在任何条件下都有一条执行路径
  - 可行性：算法每一步都必须是可行的，每一步都能通过执行有限次数完成  基本操作运算有限次实现的

  ### 2.2 算法设计的要求

  - 正确性

  > 正确性是指算法至少应该具有输入、输出和加工处理无歧义性、能够正确反映问题的需求、能够正确得到问题的正确答案
  >
  > 正确分为四个层次：
  >
  > ```
  >    1. 没有语法错误
  >    2.  输入数据能够产生满足要求的输出结果
  >    3. 非法输入数据能够得出满足规格说明名的结果
  >    4. 精心选择、甚至刁难的数据都有满足要求的输出结果
  > ```

  - 可读性  便于阅读、理解、交流
  - 健壮性  当输入数据不合法时，算法也能做出相关处理，而不是产生异常或莫名其妙的结果
  - 时间效率高和存储量低

  ### 2.3 算法效率的度量方法

  - 事后统计方法：设计好的测试数据和程序，利用计算机计时器对不同算法编制的程序的运行时间进行比较，从而确定算法效率高低  。1 必须执行程序  2，其他因素掩盖算法本质
  - 事前分析评估方法

  > 算法执行时间和增长率和问题规模 f(n) 的增长率相同
  >
  > T(n) = O(f(n))
  >
  > 称T(n)为算法的（渐进）时间复杂度
  >
  > 算法 = 控制结构 + 原操作（固有数据类型的操作）
  >
  > 算法的执行时间 = 求和 {  原操作（i）的执行次数 * 原操作（i）的执行时间 }  
  >
  > 算法的执行时间与原操作执行次数之和成正比

  > 决定的因素：和算法执行时间相关的因素
  >
  > 1. 算法采用的策略、方法
  > 2. 编译产生的代码质量
  > 3. 问题的输入规模
  > 4. 机器执行指令的速度
  > 5. 编写程序的语言
  >
  > 一个程序运行的时间，依赖于算法的好坏、问题输入的规模（输入量的多少）
  >
  > 从算法中选取一种对于所研究的问题来说 **基本操作** 的原操作，以该基本操作 **在算法中重复执行次数** 作为算法运行时间的操作的衡量标准
  >
  > 严 说这里算法执行的效率与问题的问题规模，原操作执行次数有关，但是这里问题规模具体是指什么？
  >
  > ```c++
  > int i = 1;
  > int j = 1;
  > int k = 1;
  > //两个矩阵相乘。必须要有x对应y是相同的
  > int n = strlen(a)/strlen(int);
  > //这是 x 轴
  > int        //存放
  > for(;i<=m;i++){
  >  //第一个矩阵
  >  for(;j<=n;j++){
  >      c[i][j] = 0;
  >      for(k = 1;k < n;k++){
  >          c[i][j]+=a[i][k]*b[k][j];
  >      }
  >  }
  > }
  > 
  > 
  > ```
  >
  > 例2 选择排序
  >
  > ```c
  > void select_sort(int *arr,int len){
  >  int i = 0;
  >  int j = 0
  >  for(;i<len-1;i++){
  >  //    j = i;
  >      for(k=i+1;k<len;k++){
  >          if(arr[k]<arr[i]&&k!=i)
  >              int a = arr[k];
  >              arr[k] = arr[i];
  >              arr[k] = a;
  >  
  >      }
  >  }
  > }
  > //算法思想：将该数最小的一个最前面 时间复杂度是n（n-1）/2  就是一个等差数列求和
  > ```
  >
  > 时间复杂度的取值，是将某一个循环中的一个基本操作（每一次循环都会执行的语句）取出作为复杂度的值 ==最深层语句频度
  >
  > 例3 冒泡排序
  >
  > ```c++
  > //这其实是一个选择排序
  > void bubble_sort(int *arr,int len){
  >  for(i= 0;i<len-1 && flag;i++){
  >      flag = false;
  >      for(j = i+1;j<len;j++){
  >          if(arr[i]>arr[j]){
  >              flag = true;
  >              int x = arr[i];
  >              arr[i] = arr[j];
  >              arr[j] = arr[i]
  >          }
  >      }
  >  }
  > }
  > 
  > //严   这是最屌的  关键点在与那个 change 必须要相邻的两个索引之间进行比较，如果和选择排序那样，change是无效的
  > void bubble_sort(int *arr,int len){
  >  for(i = n-1; i > 1 && charge ;i--){
  >      for(j = 0; j<i;j++){
  >          if(arr[j]>arr[j+1]){
  >              change = true;
  >              int x = arr[j];
  >              arr[j] = arr[j+1];
  >              arr[j+1] = x;
  >          }
  >      }
  >  }
  >                      
  > }
  > //基本操作是赋值操作  时间复杂度是（n(n-1)/2）--n^2 
  > //复杂度 最低是n-1 最高就是（n(n-1)/2）在没有说明的情况下我们都是以算法最坏的情况为最终结果
  > 
  > ```
  >
  > - 渐进时间复杂度 = 最坏渐进时间复杂度

  ### 2.4算法的存储空间需求

  算法的空间复杂度

    S（n） = O（g（n））

  表示随着问题的规模n的增大，算法运行所需存储量的增长率与g(n)的增长率相同

  - 算法的存储量包括：

    ```
    1. 输入数据所占空间；
    2. 程序本身所占空间
    3. 辅助变量所占空间
    ```

  > 若输入数据与所占空间只取决于问题本身，与算法无关，则只需要分析**除输入和程序之外的辅助变量所占的额外空间**
  >
  > 若所需额外空间相对于输入数据量来说是常数，则称此算法为**原地工作**
  >
  > 若所需存储量依赖于特定的输入，则通常按最坏情况考虑

  

  ## 3.线性表

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-07_212658.jpg)

  - 线性结构是一个数据元素的有序（次序）集  位置次数上有序而不是数据大小顺序上有序
  - 线性结构基本特性:

  1. 集合中必须存在唯一的一个“第一元素”
  2. 集合中必须存在唯一的一个“最后元素”
  3. 除最后元素外，均有唯一的后继；
  4. 除第一个元素之外，具有唯一的前驱；

  ### 3.1线性表的类型定义

  - 抽象数据类型线性表定义如下：

  ```
  ADT List{
      数据对象：
       D={ai|ai属于ElemSet,i = 1,2,3,4,...n,n>=0}
       {n为线性表的表长；
       称n=0时的线性表为空表}
       
       数据关系：
       R1 = {<ai-1,ai>|ai-1,ai属于D，i=2，3，4..n}
       {设线性表为（a1,a2,a3,...an）i为a在线性表中的位  
       序}
       
       基本操作：
        {结构初始化}
          InitList(&L)
          操作结果：构造一个空的线性表L
          
        {销毁结构}
          DestroyList(type *L)
          初始条件：需要线性表L存在
          操作结果：销毁线性表L
          
        {引用型操作}  操作的结果不改便这个结构
           ListEmpty(type *L)  判空
           ListLennth(type *L) 求长
           PriorElem(L,cur_e,&pre_e)  求元素前驱 cur不是第一个元素的话 并且在L中存在
           NextElem(L,cur_e,&next_e)  求元素后继
           GetElem(L,i,&e) 获取低i个元素 判断i是否》0 《L.length
           LocateElem(L,e,conpare())  求取一个与e相同的第一个元素  
           ListTraverse（L,visit()） 遍历  traverse   穿过
           
           {加工型操作}
           clearList（&L）
           PutElem（L，i，&e） 
           ListInsert（&L，i，e）
           ListDelete（&L，i，&e）
        
  }
  
  ```

  - 使用这些基本操作可以对一个线性表进行的操作

  > 例1  假设：有两个集合A和B分别用连个线性表La和Lb表示，先求一个新集合La = La∪Lb
  >
  > 上述问题可演绎为：扩大线性表La，并存在于线性表Lb中而不存在与线性表La中的数据元素，插入到线性表中La中去
  >
  > 1.从线性表Lb中一次取每一个数据元素；
  >
  > 2. 依值在线性表La中查访；
  > 3. 若不存在及插入
  >
  > 例2 已知一个非纯集合B（有重复的值），是构造集合A，使iA中只包含B所有值不相同的数据元素
  >
  > 1.初始化a
  >
  > 严说 要先对B进行排序，然后将往A中插入
  >
  > 这样的话在插入元素时，判断该元素与A中的前一个元素是否相等即可
  >
  > 便利数组需要知道数组长度，需要每一个数组的长度，尤其是a，需要往里插入数值，长度需要变得
  >
  > 
  >
  > 例3 归并连个其数据元素按值非递减有序排列线性表laLb，求得线性表Lc也具有同样的特性
  >
  > 两表长度不相同，建议使用while循环一个大循环，嵌套两个小循环，小循环是为了将某一个表还没查完，但是已经比较完，

  

  

  

    

  ### 3.2线性表类型的实现 --顺序映象

  - 使用一组地址连续的存储单元依次存放线性表中的数据元素

  线性表中的起始地址称作线性表的基地址

  以存储位置相邻表示有序对<ai-1,ai>即：

  loc(ai) = loc（ai-1）+c

  C:一个数据元素所占存储量

  所有数据元素的存储位置军取决于第一个数据元素的存储存储位置：

  loc（ai） = loc（a1）+（i-1）*c

  ```c
  #define LIST_INIT_SIZE  80 
  //线性表存储空间的出事分配量
  #define LISTINCREMENT 10
  //线性表存储空间的分配量
  type struct{
      ElemType *elem；
      int length;
      int listsize;
  }SqList;
  
  
  //声明一块堆地址使用 malloc
  L.elem = (ElemType *)malloc(LIST_INIT_SIZE*sizeof(ElemType));
  //在插入元素时，表的长度不够没使用堆，是要进行重新申请oldList+increaseList大小的数组
  newbase = (ElemType *)realloc(L.elem,(L.listSize+Listincreat)*sizeof(ElemType));
  //重新生命地址时还需要将原先旧地址指针放入参数中，是系统将不用的数据进行回收处理
      释放空间使用free（q）
   
  ```

  - 在线性表中插入数据  考虑平均情况

  假设在第 i  个元素之前插入的概率为 Pi 则在长度为 n 的线性表中插入的一个元素所需移动的元素次数的期望值

  ![](/eshmarry/dong_markdown/blob/master/img/线性插入平均移动元素值.jpg)

  - 在线性表中删除数据  考虑平均情况

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-06_211925.jpg)

  c语言数组也可以进行演示

  ### 3.3线性表类型的实现 --链式映象

  ```
   #### 一、单链表
  ```

  ​        用一组地址任意的存储单元存放线性表中的数据元素

  ​        以 **数据域**（数据元素的映象）+**指针域**（指示后继元素存储位置的） = **结点**（表示数据元素）

  - 以**结点的序列表示线性表---称作链表**
  - **头指针是指示头结点的**
  - 是由头结点的，**头结点数据部分是空**
  - **空表**  指针域为空

  ```c
  Typedef struct LNode{
      ElemType data;
      struct Lnode *next;
  }LNode,*LinkList;
  ```

  > - 在链表中获取某个位置的时候
  >
  > 1. 要判断指针下一个是否存在，
  > 2. 要获取的位置索引也需要判断，如果在查找链表的时候
  >
  > - 在链表插入数据元素
  >
  > 1. 需要先遍历链表，找到指定的 i-1（在第i位置插入数据，就要找到i-1的位置上） 位置
  > 2. 创建一个节点，将数值放在数值域上，将这个新节点的地址存放在p前驱的next（指针域）上，然后将p的那个地址存放在该节点的指针域上

  - 用链表进行数组有序去重，链表的时间复杂度是没有减少的，因为在检查前面的刚放入的元素是否和现在获取的元素是否相同，链表要从头进行查找

  - 两个有序线性表的归并，在链表的情况下

    顺序O（两表长度和）

    链表就是平方级别  （找元素时从第一个找起，for循环重新找，插入也是如此）

  - 线性表使用顺序印象时线性级的，当线性表使用链式映象表示的时候，是这两个实现的方式的时间复杂度差着平方级别的

  > - 查看上述单列表的实现操作时，存在问题；
  >
  > 1. 单链表的表长是一个隐含值；
  > 2. 在单链表的最后一个元素插入元素时，需遍历整个链表
  > 3. 在链表中，元素的**位序概念淡化**，**结点位置概念强化**
  >
  > - 改变链表的设置
  >
  > 1. 增加表长，表尾针针，当前位置的指针，三个数据域

  - 链表的进本操作：

  > ```c
  > Status InitList(LinkList &L);
  > //构造一个空的线性表L；
  > //头指针，尾指针和当前指针均指向头节点，表长为0
  > Status DestroyList(LinkList &L);
  > //销毁线性表L  销毁时要注意内存
  > 
  > Status ListEmpty(LinkList L);//判表空
  > int ListLength(LinkList L);//求表长
  > Status Prior(LinkList L);//改变当前指针指向前驱
  > //需要遍历该链表
  > Status Next(LinkList L);//改变当前指针指向其后继
  > //该指针有保持当前指针的，不用遍历，可直接获取
  > ElemType GetCurElem(LinkList L);
  > //返回当前指针所指的数据元素
  > Status LocatePos(LinkList L,int i);
  > //改变当前指针指向顶i个结点
  > Status LocateElem（LinkList L，ElemType e，Status (*compare) (ElemType,ElemType)）;
  > //若存在与e满足函数compare（）判定关系的额元素则将移动当前指针指向第一个满足条件的元素，并返回OK，否则返回Error
  > Status ListTraverse(LinkList L,Status(*visit));
  > //依次对L的每一个元素调用函数visit()
  > 
  > //加工型操作
  > Status ClearList(Linklist &L);
  > //重置为空表
  > Status SetCurElem(LinkList &L,ElemType e);
  > //更新当前指针的所☞数据元素
  > Status Append（LinkList &L，Link s）；
  > //一串结点连接到最后一个结点之后
  > Status InsAfter(LinkList &L,ElemType e);
  > //将元素e插入当前指针之后
  > Status DelAfter(LinkList &L,ElemTYpe *e);
  > //删当前指针之后的结点
  > 
  > ```
  >
  > 
  >
  > - 链式改进线性表   两组数组归并
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-07_203043.jpg)
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-07_203124.jpg)

  #### 二、其他形式链表

  ##### 1.双向链表

  - 线性表双向链表存储结构

  ```c
  typedef struct DuLNode{
      ElemType data;//数据域
      struct DuLNode *prior;
      //指向前驱的指针域
      struct DuLNode *next；
          //指向后记的指针域
  } DuLNode，*DuLinkList；
  
  //空表 前后指针域都指向他自己  都为空？？？
  
  ```

  ##### 2.循环链表

  - 最后一个结点的指针域的指针有指回第一个结点的链表

  ##### 3.双向循环链表

  

  

  ### 3.4一元多项式的表示

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-07_205229.jpg)

  - 不只是存系数，而且还要存未知数的指数

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-07_205512.jpg)

  ## 4.栈和队列

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-09_220740.jpg)

  栈顶出入数据   **后进先出**

  ### 4.1栈的类型定义

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-07_213429.jpg)

  基本操作：

  ​      initStack（&S）

  ​      DestoryStack(&S)

  ​     StatckEmpty(S)

  ​     StackLength(S)

  ​    GetTop(S,&e)

  ​    ClearSatck(&S)

  ​    Push(&S,e)

  ​    Pop(&S,&e)

  

  ### 4.2栈的应用举例

  #### 4.2.1 数制转换：

  例如将一个十进制的数转化为八进制的数

  - 算法基于原理：N = （N div d）*d + N mod d

  > 例如：（1348）十进制 = （2504）八进制
  >
  > N      N div 8        N mod 8
  >
  > 1348     168             4
  >
  > 168        21               0
  >
  > 21          2                  5
  >
  > 2            0                 2    
  >
  > 如果考虑使用数组，就要思考 索引的问题，因为谁也不知道有多少个数值，但是使用java可以使用集合，将集合倒序输出，但是集合又有无序，需要使用LinkSet   使用栈就可以很好的解决问题

  #### 4.2.2 括号匹配的检验：

  > 原括号，方括号，花括号
  >
  > 检验是否匹配的方法使用“期待的急迫程度”这一概念来描述
  >
  > 分析可能出现的不匹配的情况：
  >
  > - 到来的右括弧非所期待的；
  > - 到来的是 不速之客；
  > - 直到结束，也没有到来所期待的
  >
  > 是分别是，1不匹配，2.表达式没结束栈空了，3.表达式结束了，栈没空 
  >
  > 算法设计思想：
  >
  > 1. 凡出现左括弧，则进栈
  > 2. 凡是出现右括弧，首先检查站是否空若站控，则表明右括弧多了，否则和栈顶元素比较，若相匹配，则左括弧出栈，否则不匹配
  > 3. 表达式检验结束时，若栈空，则匹配正确，否则表明左括弧多 了

  #### 4.2.3行编辑程序问题：

  > 在电脑屏幕上敲打命令行，存储起来，可以删除修改
  >
  > 如何实现？
  >
  > 每接收一个字符及存入？{不恰当}
  >
  > - 设立一个缓冲取，用以接受用户输入的一行字符，然后逐行存入用户数据区
  > - 在用户输入一行的过程中，允许用户输入差错，并在发现有误时可以及时更正。
  >
  > 约定：假设从终端接受了这样两行字符：
  >
  > ​        whli##ilr#e（s#*s）     #号（退格符）是对前一个字符的否定
  >
  > ​        outcha@putchar（*s=#++）  @号（退行符）是对这一行前面的所有的否定
  >
  > ​       实际上是这样的
  >
  > ​         while(*s)
  >
  > ​        putchar(*s++)
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-08_211729.jpg)

  #### 4.2.4迷宫求解：

  > 通常是使用“穷举求解方法”
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-08_212555.jpg)
  >
  > - 基本思路
  >
  > 1. 若当前位置可通，纳入路径，继续前进
  > 2. 若当前位置不可通，则后退，换向探索
  > 3. 若四周均不同通，则从路径中删除
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-08_214154.jpg)
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-08_214411.jpg)

  #### 4.2.5 表达式求值：

  限于二元运算的表达式定义：

     表达式：：=（操作数）+（运算数）+（操作数）

     操作数：：=简单变量|表达式

     简单变量：：=标识符 | 无符号整数

  > 在计算机中表达式有三种不同的标志方法
  >
  > 设 Exp = S1+op+S2
  >
  > 则称 op+S1+S2为表达式的前缀表示法
  >
  > 称S1+op+S2为表达式的中缀表示法
  >
  > 称S1+S2+op为表达式的后缀表示法
  >
  > 可见运算符所在位置不同命名也不同
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-09_193017.jpg)
  >
  > - 结论：
  >
  > 1. 操作数之间的相对次序不变；
  > 2. 运算符相对次序不变   前缀后缀变了
  > 3. 中缀式是很没必要的，丢失了括弧信息，致使运算次序不确定
  > 4. 前缀式的运算规则为：连续出现的两个操作数和在他们之前且紧靠他们的运算符构成了一个最小的表达式---唯一的确定了运算顺序
  > 5. 后缀式的运算规则为：
  >
  > ​        运算符在式中的顺序恰为表达式的运算顺序；每一个运算符和在他之前出现且紧靠他的两个操作数构成一个最小的表达式
  >
  > - 如何从后缀式中求值？
  >
  > ​      先找运算符，再找操作数

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-09_200315.jpg)

  - 注意i： 一中的操作数栈为运算符栈

  #### 4.2.6 实现递归 ：

  当在一个函数的运行期间调用另一个函数时，在运行该被调用函数之前，需要完成三件事：

  1. 将所有的实参，返回地址等信息传递给被调用函数保存；
  2. 为被调用函数的局部变量分配存储区；
  3. 将控制转移到被调用函数入口。

  从被调用函数返回调用函数之前，应该完成l

  1. 保存被调用函数的计算结果
  2. 释放被调用函数的数据区
  3. 依照被调用函数保存的返回地址将控制转移到调用函数

  多个函数嵌套调用规则是：

     **后调用先返回**此时的**内存管理**实现**栈式管理**

  > 递归过程指向过程中占用的数据区，称为**递归工作栈**
  >
  > 每一层的递归参数合成一个记录，称之为**递归工作记录**
  >
  > 栈顶记录指示当前层的执行情况，称之为**当前活动记录**
  >
  > 栈顶指针称之为 当前**环境指针**
  >
  > ​           

  递归工作栈，相当于存储每一个调用自己函数，并存储自身数据，相当于玩汉诺塔游戏，三个柱子，不能将大的托盘放到小的托盘下面，就像递归，被调用不能出现在调用它的方法之前

  汉诺塔：

     ![](/eshmarry/dong_markdown/blob/master/img/2019-10-09_212345.jpg)

  ​                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              

  ### 4.3栈的类型实现

  #### 4.3.1 顺序栈

  - 类似于线性表的顺序映象实现，指向表为的指针可以作为栈顶指针

  ```c
  #define STACK_INIT_SIZE 100;
  #deine STACKINCREMENT 10;
  typedef struct{
      SElem Type *base;
      SElem Type * top;//栈顶指针实际指的是最后一个元素的后一个位置
      int stacksize;
  }SqStack;
  
  ```

  

  #### 4.3.2 链栈

  自己看书

  ### 4.4 队列的类型定义

  - 栈和队列都是一种线性表

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-09_213639.jpg)

  队头删除，队尾添加

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-09_213803.jpg)

  ### 4.4 队列类型的实现

  #### 4.4.1 链队列--链式映象

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-09_214424.jpg)

  队头指针指向的是队头元素的前一个结点，队尾指针指的是队尾元素

  当队列只有一个值得时候，删除掉最后一个数据元素时

  1. 要将队头指针域赋值为null，也就是删除的数据节点的指针域，队尾指针要指向队列的头结点，也就是队头指针值得指针结点，也就是栈顶指针所指的数据节点

  #### 4.4.2 循环队列--顺序映象

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-09_215500.jpg)

  有三个状态：  队头队尾都有可能浮动，栈只有栈顶在的浮动

  ​    1. 有数： 队头指针指向第一个元素，队尾指针指向队尾后一个元素，和栈顶指针一样

  2. 初始化的时候，两个指针都指向队头
  3. 循环队列队满  队尾指针指在队头指针的下一个  （浪费一个空间）

  循环队列满   （队尾指针+1）%maxsize = 队头指针

  循环队列空   队尾指针 = 队头指针

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-09_220253.jpg)

  问题   理发座位，排队

  **发现问题时先进先出还是先进后出**

  和线性表结构上实现同的   类型上的不同（认为的限定插入取出数据的位置）

  站和队列称为限定性的结构

  ## 5 串

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-18_201130.jpg)

  - 在程序中是以变量的形式出现的
  - 串就是将数据元素限定为字符的线性表

  #### 5.1 串的抽象数据定义

  ADT String{

  数据对象：D = {a_i|a_i属于CharacterSet，i = 1，2，3，4……n    n>=0}

   数据关系：R1 = {<a_i-1,ai>|a_i-1,a_i属于D，i = 2，3，4……n}         

  }

  - 基本操作

  ​     StrAssign(&T,chars)    串的赋值

  ​     StrCompare(S,T)  串的比较

  ​     DestroyStriing(&S)

  ​     Concat(&T,S1,S2)  串的连接

  ​     StrEmpt(S)

  ​      SubString（&Sub，S，pos，len）串的截取

  ​      Index（S，T，pos）在主传中是否存在一个字串T，返回第一次出现的位置  T的长度与pos是有相关的，当S - Pos<T就不会存在匹配

  ​      ClearString(&S)

  ​      Replace(&S,T,V)

  ​      StrDelete(&S,pos,len)

  ​      StrInsert(&S,pos,T)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-10_194006.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-10_194334.jpg)

  - 例如利用串的比较，求串长和求子串等操作实现定位函数Index

  > 基本思想：在主串S中取从第i（i的处置为pos）个字符起，长度和串T相等的字串和串T比较，若相等，则求得函数值为i，否则i值增1直至串S中不存在和串T想的的子串位置
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-10_201610.jpg)
  >
  > 注意：这个地方的什么时候是该比较循环的结束呢，是（n-m+1）

  #### 5.2 串的表示和实现

  如果在程序设计语言中，船只是作为输入或输出的常量出现，则只需要存储此串的串值，即字符序列即可。但在多数非数值处理的程序中，传也可以以变量的形式出现

  ##### 5.2.1 串的定长顺序存储表示（顺序存储映象）静态的

  ```c
  #define MAXSTRLEN 255
  typedef unsigned char Sstring [MAXSTRLEN+1];
  //0号单元存放串的长度
  //串的实际长度可在这个预定义长度的方位内随意设定，超过于一定义长度的串值则被舍去，称之为“截断”
  //在c语言中用特殊符号表示字符串的实际长度
  
  //1.再拼串的时候判断是否截断
  //2.如果盛放这两个串的全部的值，存放不全截断，就要将拷贝的时候要计算好，再进行拷贝
  
  ```

  

  ##### 5.2.2 串的堆分配存储表示（顺序存储映象）动态的

  ```c
  typedef struct{
      char *ch;//若是非空串，则按串长分配存储区，
      //否则ch为null
      int length;//串长度
  }HString;
  
  ```

  通常，**C语言中提供的串类型就是以这种存储方式实现的**。系统利用函数malloc（）和free（）进行串值空间的动态管理，为每一个新产生的串分配一个存储区。**称串值共享的存储空间为堆**，C语言中的串以一个空字符为结束符，串长是一个隐含值

  ##### 5.2.3 串的块链存储表示（链式存储映象）

  - 串的链表要给一个头指针和尾指针
  - 块链存储串的时候，不是以一个字节存储单个字符，而是一个块链存储一个子串

  ```c
  #define CHUNKSIZE 80//定义块的大小
  typedef struct Chunk{//节点结构
      char ch[CHUNKSIZE];
      struct Chunk *next;
  }Chunk;
  typedef struct{//串的链表结构
      Chunk *head ，*tail;
      int curlen;//串当前长度
  }LString;
  
  ```

  - 存储密度问题

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-10_210246.jpg)

  > 就是用一个块链结点存储一个只有一个字符的数据时，数据域占一个字节，指针域占四个字节，数据域只为整个结点大小的1/5，不值得
  >
  > 存储密度 = 数据域字长  /  整个节点的字长

  - ![](/eshmarry/dong_markdown/blob/master/img/2019-10-10_210954.jpg)

  #### 5.3 串的模式匹配（子串定位函数）

  - 这是串的一种重要操作，很多软件，若有 “编辑” 菜单项的化，则其中必有 “ 查找” 子菜单项 

  > 回忆一下串匹配（查找）的定义
  >
  > index（S，T,pos）
  >
  > 初始条件：串S，T存在，T是非空串，
  >
  > 1<=pos<=s.length
  >
  > 操作结果：若珠串S中存在和串T值相等的子串返回它在主串S第pos个字符后第一次出现的位置，否则为0

  - 下面讨论的是以定长顺序结构表示串时的几种算法

  ##### 5.3.1 简单算法(朴素的算法)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-10_212455.jpg)

  O(S.length*T.length)

  ##### 5.3.2 首尾匹配算法

  - 基于简单算法经常到最后一个才出现不同，出现了该算法
  - 先比较模式串的第一个字符
  - 再比较模式串的最后一个字符
  - 最后比较模式串中从第二个到第n-1个字符

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-10_213915.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-10_214144.jpg)

  - 那如果倒数第二是经常不一样的，怎么办？

  ###### 5.3.3 KMP算法

  - 该算法时间发咋读可以达到O（m+n）  解决了指针回溯问题

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-10_220227.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-10_220255.jpg)

  - 思想，主串和模式字串比较的时候，存在一个长串，主串和模式串的部分相等，再Si和Tj位置不相同时，因为模式串的Tj-k+1到Tj-1与主串的si-k+1 ----Si-1相同（T1到Tj-1和Si-j+Si-1
  - 都是相同的，但是要重新移动T进行匹配），你要找移位模式串，和主串重新匹配也就是说要重定义一个位置再T中使Si-k+1到Si-1位置上相同也就是和T未移动的时候T1到Tk-1要相同

  也就是在匹配范围里的相同的序列，再重新对找与T相同的序列

  - Si！=Tj   判断 Si = Tk，T1-k要与Si-k+1到Si也就是模式串中的每一个字符比较  
  - 需要求一个序列next序列数组：

  1. 要比较到主串与模式串第一个不相同的，实现跳转
  2. 这个模式串能够实现跳转，跳转到从不匹配模式串的该序列，最大与模式串序列与值相同的索引上，实现不用回溯主串，通过调整模式串
  3. 调好位置后，实现原先模式串与主串比匹配的那个位置进行比较
  4. next序列数组实现对模式串与主串在出现不匹配的情况下，最快的调整模式串，形成新的最长的匹配序列

  - 如何使用next数组 

  1. 求出模式串的next数组，将模式串与主串进行比较，比较多个后出现不同，则查找相同位置上的next数组，查看next值，进行移动模式串，如果值为3，就是移动模式的第三个位置与该不匹配的位置相对应，然后进行比较
  2. 如果比较到主串和模式串的第一个不等，next数组该位置为0，则需要主串移位与模式串比较

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-18_181906.jpg)

  如何求去模式串的next函数值  是一个递推的过程

  - 已知 next[1] = 0
  - 假设：next[j] = k;又T[j] = T[k]
  - 则：next[j+1]  = k+1 

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-18_185745.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-18_193254.jpg)

  - 特殊情况：

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-18_194015.jpg)

  1. 在模式串中求取next数组，一个为i=值 一个为j=i+1，则查看next[j]的值，结果在模式串索引为next[j]模式串的值和第j值相同

  - 更新

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-18_200950.jpg)

  ## 6.数组和广义表

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-20_190615.jpg)

  ### 6.1 数组的类型定义

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-18_201804.jpg)

  线性结构

  二维数组 ：

  基本操作：

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-18_210631.jpg)

  - value：方法根据下表找元素
  - Assign：方法 给指定下标赋值

  对数组没有插入删除的操作，最多是改变数据元素的值

  

  ### 6.2 数组的顺序表示和实现

  因为类型特点的原因：

  1. 只有引用型操作，没有加工型操作
  2. 数组是多维的结构，而存储空间是一个一维的结构《这是一个多维到一维的映象的方法》

  所以只有顺序表示

  这种映象的方式：

  1. 以行序为主（低下标优先）

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-18_213736.jpg)

  先以第三行开始：三个数组，下标索引分别为（2，3，2）

  第一组    0    1 

  第二组     0     1     2

  第三组     0      1

  取值（从第三个组开始）：000  001  010  011  020  021

  ​           100  101   110  111   120  121 

  2. 以列序为主（以高下标优先）

  以第一个数组开始

  000   100   010  110  020  120

  001    101   011  111   021  121

  地址的计算公式：（行序）

  二维

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-18_215038.jpg)

  - b2是指每一行元素个数

  推广到多维：

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-18_215246.jpg)

  ### 6.3 稀疏矩阵的压缩存储

  假设m行n列的矩阵含t个非零元素，则称稀疏因子为

  t/（m*n），通常认为稀疏因子小于等于0.05的矩阵为稀疏矩阵

  百分之九十五的零为稀疏矩阵

  - 一常规方法，以二维数组表示高阶稀疏矩阵时会产生的问题：

  1. 零值栈的空间很大
  2. 计算进行了很多和零值的运算

  - 解决：

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-18_220321.jpg)

  - 方法：

  方法1. 特殊矩阵的压缩存储：

  ​           例如：三角矩阵（上下三角矩阵）、对角矩阵（居于对角线两侧）

  方法2.随机稀疏矩阵的压缩存储：

  ​        非零元素分布不规则

     （1）三元组顺序表

  ​         ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_184512.jpg)

  - 像这样存入地址和数值，并存入行列式的一些基本信息，这个叫三元组顺序表

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_184657.jpg)

  - mu 行号，nu 列号，tu 非零元素
  - 实现了不存零元素，但是能否实现计算呢

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_185239.jpg)

  - 顺序影像上完成专置 运算

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_190639.jpg)

  - 1. 顺序表中的第一个为 1 2 3 时以为转置为2 1  3肯定是二开头的第一个，所以要找M表中第二位数据为1的个数N，然后将其插入N+1的位置上

    

    ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_191714.jpg)

    为了方便转置，创建上表，第一行为M表的列，NUM表示列值为这个数的个数，cPot是值为这个数的第一个存放在T中的位置

    算法实现，cpot随着插入到T中，如该列有了一个数值，cPot

    在该列数值上+1

    ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_192721.jpg)

  - 这是方便的，但是我想找随即一行的非零元素是很麻烦的

  - 三元组顺序表，有序的双下标法，有的是单下标法，比如三角矩阵

  （2 ）行逻辑连接的顺序表

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_193406.jpg)

  改为

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_193741.jpg)

  - 在该顺序表中，M表中列的不同数值的第一个的索引
  - 以矩阵相乘为例

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_194216.jpg)

  - 问题所在：计算完了之后要按照稀疏矩阵三元组排列好在顺序表中

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_194517.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_211941.jpg)

  只要第一个矩阵的列号与第二个矩阵的行号相乘相加

  

  > 这次改进后，可以好的求取行列式的 A*B  
  >
  > 1. 先求取出第二个矩阵的行值地址表
  > 2. 创建暂存寄存器，表B有几列创建几个，里面计算为+
  > 3. 指针 p 指 到行列式A的顺序映象地址上，然后取出该地址的列地址 i与值a1，在第二个表中的行值地址表上q指针找到对应 i 值的首地址并取出该位置上的值b1和列的值j，计算a1与b1，然后将值存入与j相同的暂存寄存器中，
  > 4. 计算完A第一个与B中的第一个后，通过过行值地址表看相对映的值下一个的地址是否是对一次相对的地址值+1，如果不是，则p指针不动，q指针往下移动，p指针指的位置进行计算，将值存入B列的相对应的行值地址表中，若果是，则A的p指针下移，如果行值与上一个不相同，则暂存寄存器的值计算出结果，行由A的行值决定，列以暂存寄存器编号决定，存入C的顺序表中
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_212131.jpg)
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_212312.jpg)
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_212427.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-19_213427.jpg)

  上面我们得到的矩阵都是新建立的，没有元素的移动，如果在计算的时候插入几个非零元，表现形式有变化了，若果是做两个矩阵相加，将A、B两个矩阵结果加到A上，而不是新建一个，由改成链式

  **（3）十字链表**

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-20_175639.jpg)

  - 同一行用一个指针，同一列也用一个指针
  - 行列指针的头指针放在一个一维数组中
  - 这样的优点：方便增加、删除

  ​            1. 这样插入删除，涉及两个来链表的改变  

  ### 6.4 广义表的类型定义

  - 广义表是特殊的线性结构

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_194608.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_195048.jpg)

  - 原子：只有单个元素
  - 子表：还是一个广义表
  - 空表：长度为零  深度为1  A = （）

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_195734.jpg)

  ### 6.5 广义表的表示方法

  - 构造存储结构

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_201227.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_201321.jpg)

  - 广义表表头是是一个原子结点，表尾是一个广义表结点
  - ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_201642.jpg)
  - 第二种构造方法

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_201932.jpg)

   

  

  ### 6.6 广义表操作的递归函数

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_202300.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_202344.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_202549.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_203006.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_203652.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_204256.jpg)

  例题1：求广义表的深度：

  **广义表的深度 = max{子表深度}+1**

  **空表深度为1，原子深度为0**

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_204625.jpg)

  

  

  例题2：复制广义表：

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-31_192045.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-31_192109.jpg)

  例题3：创建广义表的存储结构：

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-31_192533.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-31_193137.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-31_193242.jpg)

  

  

  - 算法 删除单链表中所有值为x的数据元素（与广义表删除结点相对比）

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-31_200919.jpg)

  广义表的就是广义的线性表、

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-31_201135.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-31_201513.jpg)

  - 看清广义表图样子，如果删除的是原子，就是删除的是两个结点，一个是该广义表头一个子表的头结点

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-31_202432.jpg)

  - if

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-31_202808.jpg)

  - else

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-31_202927.jpg)

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-11-01_194409.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-11-01_194856.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-11-01_195616.jpg)

  - 函数写成单支树是没必要的 1. 递归深度深，2.占存储是非常大的
  - F1 = 1   F0 = 0     Fn = F（n-1）+F（n-2）  n>= 2,求F7   不能用递归，重复节点太多

  递归式从上往下，递推是从下往上

  ![](/eshmarry/dong_markdown/blob/master/img/2019-11-01_200358.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-11-01_200752.jpg)

  

  ## 7.树和二叉树

  

  

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_200531.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_200618.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_200737.jpg)

  - 广义表是线性结构
  - 树型结构 

  ### 7.1树的类型定义

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-20_191606.jpg)

  是有向的，有前驱后继

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-20_192650.jpg)

  

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-20_194254.jpg)

  - 树深度：树中叶子结点所在最大层次
  - 树的基本操作：查找、插入、删除

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-20_194558.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-20_194902.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-20_195042.jpg)

  

  有向树：

  1. 有确定的根
  2. 树根和子树根之间为有向关系

  有序树和无序树的区别？子树之间是否存在次序关系（默认为无序树）

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-20_200946.jpg)

  - 以上这两棵树，在无序下是等同的，因为子树相同只是无需
  - 线性结构与树结构区别

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-20_201237.jpg)

  

  ### 7.2 二叉树的类型定义

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-20_201506.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-20_201831.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_205448.jpg)

  - ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_205554.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_210004.jpg)

  - 两类特殊的二叉树：

  1. 满二叉树：指的是深度为K且含有2^K-1个节点的二叉树（不存在度为1的结点，叶子节点只有最后一层是）

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_212237.jpg)

  完全二叉树，就是在满二叉树上进行行上编号，进行1-n排列，不管n怎么取，都是按照满二叉树进行编号取得

  下取整：

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_212809.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-22_194932.jpg)

  - 二叉树是从从上到下且从左到有右进行的1至n的编号
  - 若 i -1 则该结点时二叉树的根，，编号i/2的结点为双亲结点
  - 2i>n,该节点为左孩子结点

  ### 7.3 二叉树的存储结构

  #### 7.3.1二叉树的顺序存储表示

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-22_195907.jpg)

  - 怎样将层次的关系，用一维数组来表示

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-22_200159.jpg)

  - 通过性质五是可以计算的

  #### 7.3.2  二叉树的链式存储表示

  1. 二叉链表

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-22_203316.jpg)

  ​        让双亲信息隐含在内

  2. 双亲链表

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-22_210104.jpg)

  创建一个BPTNode，存取信息，该节点的数据，父节点位置，是左孩子还是右孩子标志

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-22_212748.jpg)

  

  3. 三叉链表

  ​         加一个指针域指到双亲

  4. 线索链表

  

  ### 7.4 二叉树的遍历

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-22_213011.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-22_213127.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-22_213536.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-22_213629.jpg)

  - 算法递归的描述：

    先序遍历

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-22_215300.jpg)

  

  - 非递归
  - 中序遍历，先访问根结点

  1. 先访问根（访问记输出）节点，判断A是否右左子树，有的话，将A点存入栈中，然后继续下访问 B ，无左子树，不存入栈中，继续访问C，C有左子树存入栈中，继续访问D，D无左子树，不入栈，，现在开始栈的弹出操作，先是C，然后访问C的右结点，无继续弹栈，然后访问A
  2. ![](/eshmarry/dong_markdown/blob/master/img/2019-10-22_221426.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-22_221513.jpg)

  ##### 遍历二叉树的应用举例

  1. ![](/eshmarry/dong_markdown/blob/master/img/2019-10-23_192645.jpg)
  2. 求二叉树的深度

  - 左右子树最大深度+1
  - ![](/eshmarry/dong_markdown/blob/master/img/2019-10-23_194629.jpg)

  

  3. 复制二叉树：

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-23_195104.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-23_195257.jpg)

  4 . 建立二叉树的存储结构

     （1）按给定的先序序列创建二叉链表

  ​         加上空格的先序序列的一个字符串；来 创建   A B C^ ^ ^DE^ ^ ^

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-23_200938.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-23_201016.jpg)

  （2）按给定的表达式构建相应的二叉树（直接根据表达式建树，而不是改变表达式再建树）

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-23_204518.jpg)

  - 先缀表达式：是将运算符放在二个操作数之间，与先序遍历相结合 
  - 那如何创建呢

  

  2. 中缀表达式构建二叉树：通过结合两个栈，一个运算符栈，一个操作数栈地址栈（**子树的栈**），结合创建二叉树

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-23_212841.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-23_213223.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-23_213255.jpg)

  

  后缀表达式：

  中序与任何一种其他序列一定能找到一棵二叉 树

  - 由已知的二叉树的先序和中序序列建树

  已知二叉树的  先序序列：abcdefg  中序序列 cdbaeg f

  

  ### 7.5 线索二叉树

  ##### 何为线索二叉树？

  遍历二叉树的结果是，求得节点的一个线性序列

  - 在线性序列中的**前驱**和**后记**的指针称作**线索**
  - 包含线索的存储结构称作**线索链表**
  - 于其相应的二叉树：**线索二叉树**

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_195242.jpg)

  - 粉红线是前驱，紫线是后继  先序化线索二叉树

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_195512.jpg)

  - 中序化线索二叉树

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_195707.jpg)

  - 后序化线索二叉树

  > 线索化二叉树是在二叉树上进行的
  >
  > 特点：
  >
  > 1. 前驱指针加在左子树是空的时候
  > 2. 后继线索加在右子树是空的
  >
  > 判断：
  >
  > 1. n个节点的二叉树一共有n+1个空结点
  >
  > 在n个结点的二叉树上一共有n个线连接起每一个结点，但是一共有2n个结点域，也就是说
  >
  > 3. 二叉树上的指针域是公用的，如果该二叉树没有左右子树，左指针域指向它的前驱，右指针域指向它的后继，也就就是说在节点上还要加上左右指针域的存放的是否为子树的地址的标志
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_202817.jpg)
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_202903.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_202947.jpg)

  

  ##### 线索链表的遍历算法：

  - 这样的双向链表上遍历就不需要栈

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_203258.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_203346.jpg)

  

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_203431.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_203934.jpg)

  ##### 如何建立线索二叉树？

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_204113.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_204206.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_204911.jpg)

  ### 7.6 树和森林的表示方法

  - 树的操纵都是通过二叉树来操作
  - **树的三种存储结构**

  1. 双亲表示法

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_205529.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_205646.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_205846.jpg)

  

  2. 孩子链表表示法

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_205943.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_210117.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_210223.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_210307.jpg)

  

   

  3. 树的二叉链表  孩子兄弟表示法（存储表示法）

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_210743.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_210853.jpg)

  左孩子是孩子，右孩子是兄弟 ，这是将树变为二叉树（只包含左子树），这将会成为森林变二叉树的依据

  ##### 7.7.1森林和二叉树的对应关系

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_213202.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-24_213446.jpg)

  > 由二叉树的兄弟表示法，链表表示法（将兄弟连成一个横向，**左下侧是孩子，右下侧是兄弟**）
  >
  > - 二叉树的根节点复制成第一棵树的根节点，形成一个只有左子树的二叉树，下一个树的做成该二叉树的右子树，

  > 二叉树转为森林
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-25_191653.jpg)

  ### 7.7 树和森林的遍历

  - 树的遍历：三条搜索路径，每个节点都要访问，每个节点只访问一次

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-25_192044.jpg)

   ![](/eshmarry/dong_markdown/blob/master/img/2019-10-25_192512.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-25_192744.jpg)

  - 树的先序 访问：先访问树的根节点，然后访问在根节点下的森林，然后先访问其中的第一棵树，使用先序遍历，访问完了，将下一棵树，也是这样进行访问的

  - ![](/eshmarry/dong_markdown/blob/master/img/2019-10-25_193336.jpg)

  - 树和森林的遍历

    1. 后序遍历和中序遍历是相同的，是一样的

    > 都是先访问第一棵树的并该树进行后根序遍历
    >
    > 这个地方将访问完A的时候访问左侧第一个树，并其模仿为二叉树的中序遍历，（因为是将EF看作为截断看作森林为B的左子树，B为根节点，剩余的看作为B的右节点，是这样的）
    >
    > 
    >
    > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-25_200924.jpg)
    >
    > 求取二叉树的深度，后序遍历，取最大，再+1
    >
    > 
    >
    > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-25_202858.jpg)
    >
    > - h1 是左子树森林森林，h2是右子树森林的深度
    >
    > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-25_203832.jpg)

    输出所有从根节点到叶子节点的路径（需要栈）

    ![](/eshmarry/dong_markdown/blob/master/img/2019-10-25_210753.jpg)

    ![](/eshmarry/dong_markdown/blob/master/img/2019-10-25_211336.jpg)

    ![](/eshmarry/dong_markdown/blob/master/img/2019-10-25_212328.jpg)

    - 因为树也可以用二叉树表示，所以这个路径是可以用于二叉树的   **【不对】**   因为二叉树表示叶子结点不是真正树的叶子结点

    > 如何通过二叉树来看树的叶子结点
    >
    > 二叉树的左子树空就是树的叶子结点

    - **遍历树的路径的时候，使用二叉链表表示的的方法就应该（上图）遍历完傻瓜的左子树时候开始退栈，遍历b的右子树的时候，就应该将b也弹出栈**  C G I 的右子树也如此

    这是对森林的遍历树结点 

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-25_213727.jpg)

  

  建树的存储结构算法：

    ![](/eshmarry/dong_markdown/blob/master/img/2019-10-25_215509.jpg)

  - 左侧为父母节点，右侧为当前节点，按照层次结构从左往右

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_190124.jpg)

  - 右下角是是一个队列盛放创建的已经创建结点，创建的结点进行保存

  先按层次遍历，创建结点

  - ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_184745.jpg)
  - ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_185013.jpg)

  ### 7.8哈夫曼树和哈夫曼编码

  ##### 最优树（哈夫曼树）的定义

  - 结点的路径长度定义：从根结点到该节点的路径上分支的数目
  - 树的路径长度：树中的每一个结点的路径长度之和
  - 树的带权路径长度：书中所有叶子节点带权路径长度之和

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_194151.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_194327.jpg)

  ##### 如何构造最优树

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_195246.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_195335.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_195407.jpg)

  ##### 前缀编码

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_195443.jpg)

  - 等长编码  A 00  B 01 C10 D 11  
  - 不等长编码：

  00 01 11 10 01 10 00   这是适合等长编码，器中每一个编码出现的概率是相同的

  哈夫曼 = 最优二叉树

  ### 8 图

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-30_193936.jpg)

  #### 8.1 抽象数据类型图的定义

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_201430.jpg)

  - 图上任何一个点都可以看做为顶点
  - 彼此之间地位是相等的

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_201658.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_201828.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_201912.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_202102.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_202252.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_202449.jpg)

  - 树的度为：子树的个数

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_202545.jpg)

  - **简单路径：**从节点A到结点B的路径上所经过的结点不会重复出现
  - **回路（简单回路）**： 若A= B的话

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_202930.jpg)

  - **连通图**：图中任意两个结点之间都有路径相通
  - **连通分量**：若**无向图**为**非连通图**，则途中各个极大联通子图称作此图的连通分量
  - **强连通图**：**有向图**中任意两个结点存在一条有向路径
  - **强连通分量**：是**有向图**的连通分量

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_203632.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_204344.jpg)

  - 创建一个图，要给出图的顶点的集合，和弧的集合

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_204635.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_204754.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_205023.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_205130.jpg)

  

  #### 8.2图的存储表示

  1. 图的数组存储表示

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_205351.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_205624.jpg)

  2. 图的邻接表存储表示

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_205913.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_210052.jpg)

  - 无向图：表示的边是重复的
  - 逆向邻接表

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_211308.jpg)

  - 在正向邻接表中能找到他指向别的顶点的的弧，在逆向邻接表中，能找指向它的弧，这样我希望你能够同时得到这两个 功能

  3. 有向图的十字链表

    结点：  数据域（1）  指针域  |  数据域（2） 指针域

  数据域为1的指针域指向弧指向它的结点的地址

  数据域2 为指针域为它指向别的弧的节点的地址

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_213332.jpg)

  - 横向为指向别的，竖的为别的指向它的

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_212957.jpg)

  4. 无向图的**邻接表多重表**存储表示

  - 将无向图多余的边用一条表示

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_214415.jpg)

  #### 8.3图的遍历

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_214829.jpg)

  - 深度优先遍历

  > 如果该图是连通图的话肯定能够遍历整个图
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-26_215200.jpg)

  - 与树的先根遍历是一样的，但与树不相同的是，图的深度遍历有重复结点出现
  - DFS与树的不相同 检查邻接点是否被访问过，在每个节点上做上是否访问过的标志
  - 连通图

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_185805.jpg)

  - 非连通图

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_190350.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_190816.jpg)

  - 就是访问每一个开始的点的邻接点
  - 通过深度优先遍历生成的右上的树称为深度优先生成树

  

  - 广度优先遍历

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_191348.jpg)

  - 先访问一个结点，就把该结点的所有的邻接点访问完，然后就按照上面访问邻接点的顺序进行访问相应点的邻接点
  - 就是按照到访问最初访问节点的路径长短来进行访问，先访问路径为1的再访问路径为2的，就是到达最初访问节点的邻接点的路径为1的

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_192542.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_193339.jpg)

  

  - 题例：
  - 深度和广度都可以找到路径

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_202710.jpg)

  - 广度可以找到最短的一条路径
  - 找最短路径：改进广度优先遍历，将广度优先遍历的队列进行改进，如下图，加上被指向的邻接点，到指向它的指针，这样就可以找到，是谁遍历到他的，这样可以找到源头，方便找最短路径
  - 队列在树的创建时候用到，使用树的二叉树表示的时候，加上一个表

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_203655.jpg)

  - 第一次使用双向链表，而且是跳跃的

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_204321.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_204442.jpg)

  #### 8.4最小生成树

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_213132.jpg)

  - 最小生成树是作用在：**无向网**

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_204743.jpg)

  - 构成的是一个连同的无环的网
  - 算法一：普利姆算法：

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_205442.jpg)

  > 从第一个顶点中从可选的边中选一个权值最小的边
  >
  > 是遍历邻接矩阵的
  >
  > ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_210626.jpg)
  >
  > 在主键生成树上加节点，是每一次加进去连通的权值最小

  算法二：克鲁斯卡尔算法

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_212131.jpg)

  - 点都先罗列出来，选取边选取权值最小的可选边，然后判断是否产生回路
  - 图上的权值进行排队是要先进行排序的

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_212540.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_212638.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-27_212308.jpg)

  #### 8.5重（双）连通图和关节点

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-28_195255.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-28_195421.jpg)

  - 没有关节点的连通图为双连通图
  - 深度优先遍历

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-28_195815.jpg)

  - 如果生出树有两个边证明，访问子树数据只能通过这个结点
  - 回边的作用，如果没有回边，没有直接连接到指定节点，则该结点不能直接与指定节点相连   例如 e可以与c相连，但不可以与a直接相连

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-28_200905.jpg)

  - 这是看生成树根是不是根节点

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-28_201014.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-28_201609.jpg)

  

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-28_203031.jpg)

  - 原始排序  未加回边

  从第一个没有孩子节点的生成树往根节点进行遍历，求取相关值，做成为 

  该节点low值 =（ 求取本身的访问次序，子树根low值，与该结点有回边相连的的次序值（没有回边的默认先序过来的次序为回边值））取最小

  

  举例子  low（e） = { 5，0，3  }   就是三了

  low（d） = {4，3，3} 就是三了

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-28_204055.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-28_204459.jpg)

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-28_204736.jpg)

  #### 8.6两点之间的最短路径问题

  - 从原点到其余各点的最短路径

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-28_205249.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-28_205423.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-28_205631.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-28_210414.jpg)

  

  - 问题二   **每一对顶点间最短路径：**

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_184749.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_185036.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_185114.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_190845.jpg)

  - 是通过逐渐在原先搭配中，添加中介，按照节点循序，例如

  B->A 没有路径，当中介增加到C的时候，就有了，因为存在B->C和C->A所以就像加，这样相加的结果比之前原先就有的结果小，就会替换，因为这个求图的每一个节点到其他结点最短路径，需要权值邻接矩阵，路线邻接矩阵

  #### 8.7拓扑排序

  - 解决有向图

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_191056.jpg)

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_191246.jpg)

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_191504.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_195858.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_200025.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_192306.jpg)

  - 求取有向图图中入度为0的结点

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_192437.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_192535.jpg)

  #### 8.8关键路径

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_201016.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_201211.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_201312.jpg)

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_201953.jpg)

  - 关键路径是在拓扑排序上进行的

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_202830.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_203352.jpg)

  - 最早开始时间（ee）和最晚开始时间（el）**相同**的就是**关键事件**
  - ![](/eshmarry/dong_markdown/blob/master/img/2019-10-29_203740.jpg)

  ## 真题

  #### 线性类题

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_191000.jpg)

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_191025.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_191301.jpg)

  

  

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_192534.jpg)

  - 从空栈到空栈，
  - 考虑栈满的化考虑到如何实现的问题
  - ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_192726.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_192510.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_193055.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_193419.jpg)

  - 模拟栈

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_194337.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_194517.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_194640.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_195855.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_200819.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_201331.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_201517.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_201747.jpg)

  - 思路：可以通过该字符串的每一个去掉首字母后进行next函数运算，当取到next就函数值最长的就是，14个字符的话，要进行13次next函数计算，计算出，最长的next函数组中最大的数字

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_203200.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-10-21_204222.jpg)

  #### 非线性类

  - 遍历时所有非线性结构（二叉树，树，图，广义表）的操作基础
  - 不同的应用需要不同的搜索路径

  ![](/eshmarry/dong_markdown/blob/master/img/2019-11-01_201501.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-11-01_201641.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-11-01_202224.jpg)

  - （上面的）使用的先序

  ![](/eshmarry/dong_markdown/blob/master/img/2019-11-01_202545.jpg)

  ![](/eshmarry/dong_markdown/blob/master/img/2019-11-01_202713.jpg)

  - disp是删除该子树所有孩子，包括释放

  ![](/eshmarry/dong_markdown/blob/master/img/2019-11-01_203255.jpg)

  - 如果子树根节点的算术运算符的优先级低于跟的运算符的优先级，则需要加括号

  ![](/eshmarry/dong_markdown/blob/master/img/2019-11-01_203559.jpg)

  - precede函数是判断运算符的优先级