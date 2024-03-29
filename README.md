- - # 数据结构

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

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-07_212658.jpg)

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

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/线性插入平均移动元素值.jpg)

    - 在线性表中删除数据  考虑平均情况

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-06_211925.jpg)

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
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-07_203043.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-07_203124.jpg)

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

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-07_205229.jpg)

    - 不只是存系数，而且还要存未知数的指数

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-07_205512.jpg)

    ## 4.栈和队列

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-09_220740.jpg)

    栈顶出入数据   **后进先出**

    ### 4.1栈的类型定义

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-07_213429.jpg)

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
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-08_211729.jpg)

    #### 4.2.4迷宫求解：

    > 通常是使用“穷举求解方法”
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-08_212555.jpg)
    >
    > - 基本思路
    >
    > 1. 若当前位置可通，纳入路径，继续前进
    > 2. 若当前位置不可通，则后退，换向探索
    > 3. 若四周均不同通，则从路径中删除
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-08_214154.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-08_214411.jpg)

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
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-09_193017.jpg)
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

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-09_200315.jpg)

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

       ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-09_212345.jpg)

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

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-09_213639.jpg)

    队头删除，队尾添加

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-09_213803.jpg)

    ### 4.4 队列类型的实现

    #### 4.4.1 链队列--链式映象

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-09_214424.jpg)

    队头指针指向的是队头元素的前一个结点，队尾指针指的是队尾元素

    当队列只有一个值得时候，删除掉最后一个数据元素时

    1. 要将队头指针域赋值为null，也就是删除的数据节点的指针域，队尾指针要指向队列的头结点，也就是队头指针值得指针结点，也就是栈顶指针所指的数据节点

    #### 4.4.2 循环队列--顺序映象

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-09_215500.jpg)

    有三个状态：  队头队尾都有可能浮动，栈只有栈顶在的浮动

    ​    1. 有数： 队头指针指向第一个元素，队尾指针指向队尾后一个元素，和栈顶指针一样

    2. 初始化的时候，两个指针都指向队头
    3. 循环队列队满  队尾指针指在队头指针的下一个  （浪费一个空间）

    循环队列满   （队尾指针+1）%maxsize = 队头指针

    循环队列空   队尾指针 = 队头指针

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-09_220253.jpg)

    问题   理发座位，排队

    **发现问题时先进先出还是先进后出**

    和线性表结构上实现同的   类型上的不同（认为的限定插入取出数据的位置）

    站和队列称为限定性的结构

    ## 5 串

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-18_201130.jpg)

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

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-10_194006.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-10_194334.jpg)

    - 例如利用串的比较，求串长和求子串等操作实现定位函数Index

    > 基本思想：在主串S中取从第i（i的处置为pos）个字符起，长度和串T相等的字串和串T比较，若相等，则求得函数值为i，否则i值增1直至串S中不存在和串T想的的子串位置
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-10_201610.jpg)
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

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-10_210246.jpg)

    > 就是用一个块链结点存储一个只有一个字符的数据时，数据域占一个字节，指针域占四个字节，数据域只为整个结点大小的1/5，不值得
    >
    > 存储密度 = 数据域字长  /  整个节点的字长

    - ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-10_210954.jpg)

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

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-10_212455.jpg)

    O(S.length*T.length)

    ##### 5.3.2 首尾匹配算法

    - 基于简单算法经常到最后一个才出现不同，出现了该算法
    - 先比较模式串的第一个字符
    - 再比较模式串的最后一个字符
    - 最后比较模式串中从第二个到第n-1个字符

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-10_213915.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-10_214144.jpg)

    - 那如果倒数第二是经常不一样的，怎么办？

    ###### 5.3.3 KMP算法

    - 该算法时间发咋读可以达到O（m+n）  解决了指针回溯问题

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-10_220227.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-10_220255.jpg)

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

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-18_181906.jpg)

    如何求去模式串的next函数值  是一个递推的过程

    - 已知 next[1] = 0
    - 假设：next[j] = k;又T[j] = T[k]
    - 则：next[j+1]  = k+1 

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-18_185745.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-18_193254.jpg)

    - 特殊情况：

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-18_194015.jpg)

    1. 在模式串中求取next数组，一个为i=值 一个为j=i+1，则查看next[j]的值，结果在模式串索引为next[j]模式串的值和第j值相同

    - 更新

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-18_200950.jpg)

    ## 6.数组和广义表

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-20_190615.jpg)

    ### 6.1 数组的类型定义

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-18_201804.jpg)

    线性结构

    二维数组 ：

    基本操作：

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-18_210631.jpg)

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

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-18_213736.jpg)

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

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-18_215038.jpg)

    - b2是指每一行元素个数

    推广到多维：

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-18_215246.jpg)

    ### 6.3 稀疏矩阵的压缩存储

    假设m行n列的矩阵含t个非零元素，则称稀疏因子为

    t/（m*n），通常认为稀疏因子小于等于0.05的矩阵为稀疏矩阵

    百分之九十五的零为稀疏矩阵

    - 一常规方法，以二维数组表示高阶稀疏矩阵时会产生的问题：

    1. 零值栈的空间很大
    2. 计算进行了很多和零值的运算

    - 解决：

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-18_220321.jpg)

    - 方法：

    方法1. 特殊矩阵的压缩存储：

    ​           例如：三角矩阵（上下三角矩阵）、对角矩阵（居于对角线两侧）

    方法2.随机稀疏矩阵的压缩存储：

    ​        非零元素分布不规则

       （1）三元组顺序表

    ​         ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_184512.jpg)

    - 像这样存入地址和数值，并存入行列式的一些基本信息，这个叫三元组顺序表

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_184657.jpg)

    - mu 行号，nu 列号，tu 非零元素
    - 实现了不存零元素，但是能否实现计算呢

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_185239.jpg)

    - 顺序影像上完成专置 运算

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_190639.jpg)

    - 1. 顺序表中的第一个为 1 2 3 时以为转置为2 1  3肯定是二开头的第一个，所以要找M表中第二位数据为1的个数N，然后将其插入N+1的位置上

      

      ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_191714.jpg)

      为了方便转置，创建上表，第一行为M表的列，NUM表示列值为这个数的个数，cPot是值为这个数的第一个存放在T中的位置

      算法实现，cpot随着插入到T中，如该列有了一个数值，cPot

      在该列数值上+1

      ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_192721.jpg)

    - 这是方便的，但是我想找随即一行的非零元素是很麻烦的

    - 三元组顺序表，有序的双下标法，有的是单下标法，比如三角矩阵

    （2 ）行逻辑连接的顺序表

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_193406.jpg)

    改为

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_193741.jpg)

    - 在该顺序表中，M表中列的不同数值的第一个的索引
    - 以矩阵相乘为例

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_194216.jpg)

    - 问题所在：计算完了之后要按照稀疏矩阵三元组排列好在顺序表中

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_194517.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_211941.jpg)

    只要第一个矩阵的列号与第二个矩阵的行号相乘相加

    

    > 这次改进后，可以好的求取行列式的 A*B  
    >
    > 1. 先求取出第二个矩阵的行值地址表
    > 2. 创建暂存寄存器，表B有几列创建几个，里面计算为+
    > 3. 指针 p 指 到行列式A的顺序映象地址上，然后取出该地址的列地址 i与值a1，在第二个表中的行值地址表上q指针找到对应 i 值的首地址并取出该位置上的值b1和列的值j，计算a1与b1，然后将值存入与j相同的暂存寄存器中，
    > 4. 计算完A第一个与B中的第一个后，通过过行值地址表看相对映的值下一个的地址是否是对一次相对的地址值+1，如果不是，则p指针不动，q指针往下移动，p指针指的位置进行计算，将值存入B列的相对应的行值地址表中，若果是，则A的p指针下移，如果行值与上一个不相同，则暂存寄存器的值计算出结果，行由A的行值决定，列以暂存寄存器编号决定，存入C的顺序表中
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_212131.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_212312.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_212427.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-19_213427.jpg)

    上面我们得到的矩阵都是新建立的，没有元素的移动，如果在计算的时候插入几个非零元，表现形式有变化了，若果是做两个矩阵相加，将A、B两个矩阵结果加到A上，而不是新建一个，由改成链式

    **（3）十字链表**

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-20_175639.jpg)

    - 同一行用一个指针，同一列也用一个指针
    - 行列指针的头指针放在一个一维数组中
    - 这样的优点：方便增加、删除

    ​            1. 这样插入删除，涉及两个来链表的改变  

    ### 6.4 广义表的类型定义

    - 广义表是特殊的线性结构

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_194608.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_195048.jpg)

    - 原子：只有单个元素
    - 子表：还是一个广义表
    - 空表：长度为零  深度为1  A = （）

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_195734.jpg)

    ### 6.5 广义表的表示方法

    - 构造存储结构

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_201227.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_201321.jpg)

    - 广义表表头是是一个原子结点，表尾是一个广义表结点
    - ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_201642.jpg)
    - 第二种构造方法

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_201932.jpg)

     

    

    ### 6.6 广义表操作的递归函数

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_202300.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_202344.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_202549.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_203006.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_203652.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_204256.jpg)

    例题1：求广义表的深度：

    **广义表的深度 = max{子表深度}+1**

    **空表深度为1，原子深度为0**

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_204625.jpg)

    

    

    例题2：复制广义表：

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-31_192045.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-31_192109.jpg)

    例题3：创建广义表的存储结构：

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-31_192533.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-31_193137.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-31_193242.jpg)

    

    

    - 算法 删除单链表中所有值为x的数据元素（与广义表删除结点相对比）

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-31_200919.jpg)

    广义表的就是广义的线性表、

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-31_201135.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-31_201513.jpg)

    - 看清广义表图样子，如果删除的是原子，就是删除的是两个结点，一个是该广义表头一个子表的头结点

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-31_202432.jpg)

    - if

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-31_202808.jpg)

    - else

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-31_202927.jpg)

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-01_194409.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-01_194856.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-01_195616.jpg)

    - 函数写成单支树是没必要的 1. 递归深度深，2.占存储是非常大的
    - F1 = 1   F0 = 0     Fn = F（n-1）+F（n-2）  n>= 2,求F7   不能用递归，重复节点太多

    递归式从上往下，递推是从下往上

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-01_200358.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-01_200752.jpg)

    

    ## 7.树和二叉树

    

    

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_200531.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_200618.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_200737.jpg)

    - 广义表是线性结构
    - 树型结构 

    ### 7.1树的类型定义

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-20_191606.jpg)

    是有向的，有前驱后继

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-20_192650.jpg)

    

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-20_194254.jpg)

    - 树深度：树中叶子结点所在最大层次
    - 树的基本操作：查找、插入、删除

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-20_194558.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-20_194902.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-20_195042.jpg)

    

    有向树：

    1. 有确定的根
    2. 树根和子树根之间为有向关系

    有序树和无序树的区别？子树之间是否存在次序关系（默认为无序树）

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-20_200946.jpg)

    - 以上这两棵树，在无序下是等同的，因为子树相同只是无需
    - 线性结构与树结构区别

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-20_201237.jpg)

    

    ### 7.2 二叉树的类型定义

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-20_201506.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-20_201831.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_205448.jpg)

    - ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_205554.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_210004.jpg)

    - 两类特殊的二叉树：

    1. 满二叉树：指的是深度为K且含有2^K-1个节点的二叉树（不存在度为1的结点，叶子节点只有最后一层是）

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_212237.jpg)

    完全二叉树，就是在满二叉树上进行行上编号，进行1-n排列，不管n怎么取，都是按照满二叉树进行编号取得

    下取整：

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_212809.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-22_194932.jpg)

    - 二叉树是从从上到下且从左到有右进行的1至n的编号
    - 若 i -1 则该结点时二叉树的根，，编号i/2的结点为双亲结点
    - 2i>n,该节点为左孩子结点

    ### 7.3 二叉树的存储结构

    #### 7.3.1二叉树的顺序存储表示

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-22_195907.jpg)

    - 怎样将层次的关系，用一维数组来表示

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-22_200159.jpg)

    - 通过性质五是可以计算的

    #### 7.3.2  二叉树的链式存储表示

    1. 二叉链表

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-22_203316.jpg)

    ​        让双亲信息隐含在内

    2. 双亲链表

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-22_210104.jpg)

    创建一个BPTNode，存取信息，该节点的数据，父节点位置，是左孩子还是右孩子标志

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-22_212748.jpg)

    

    3. 三叉链表

    ​         加一个指针域指到双亲

    4. 线索链表

    

    ### 7.4 二叉树的遍历

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-22_213011.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-22_213127.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-22_213536.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-22_213629.jpg)

    - 算法递归的描述：

      先序遍历

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-22_215300.jpg)

    

    - 非递归
    - 中序遍历，先访问根结点

    1. 先访问根（访问记输出）节点，判断A是否右左子树，有的话，将A点存入栈中，然后继续下访问 B ，无左子树，不存入栈中，继续访问C，C有左子树存入栈中，继续访问D，D无左子树，不入栈，，现在开始栈的弹出操作，先是C，然后访问C的右结点，无继续弹栈，然后访问A
    2. ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-22_221426.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-22_221513.jpg)

    ##### 遍历二叉树的应用举例

    1. ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-23_192645.jpg)
    2. 求二叉树的深度

    - 左右子树最大深度+1
    - ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-23_194629.jpg)

    

    3. 复制二叉树：

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-23_195104.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-23_195257.jpg)

    4 . 建立二叉树的存储结构

       （1）按给定的先序序列创建二叉链表

    ​         加上空格的先序序列的一个字符串；来 创建   A B C^ ^ ^DE^ ^ ^

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-23_200938.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-23_201016.jpg)

    （2）按给定的表达式构建相应的二叉树（直接根据表达式建树，而不是改变表达式再建树）

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-23_204518.jpg)

    - 先缀表达式：是将运算符放在二个操作数之间，与先序遍历相结合 
    - 那如何创建呢

    

    2. 中缀表达式构建二叉树：通过结合两个栈，一个运算符栈，一个操作数栈地址栈（**子树的栈**），结合创建二叉树

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-23_212841.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-23_213223.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-23_213255.jpg)

    

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

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_195242.jpg)

    - 粉红线是前驱，紫线是后继  先序化线索二叉树

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_195512.jpg)

    - 中序化线索二叉树

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_195707.jpg)

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
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_202817.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_202903.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_202947.jpg)

    

    ##### 线索链表的遍历算法：

    - 这样的双向链表上遍历就不需要栈

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_203258.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_203346.jpg)

    

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_203431.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_203934.jpg)

    ##### 如何建立线索二叉树？

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_204113.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_204206.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_204911.jpg)

    ### 7.6 树和森林的表示方法

    - 树的操纵都是通过二叉树来操作
    - **树的三种存储结构**

    1. 双亲表示法

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_205529.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_205646.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_205846.jpg)

    

    2. 孩子链表表示法

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_205943.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_210117.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_210223.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_210307.jpg)

    

     

    3. 树的二叉链表  孩子兄弟表示法（存储表示法）

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_210743.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_210853.jpg)

    左孩子是孩子，右孩子是兄弟 ，这是将树变为二叉树（只包含左子树），这将会成为森林变二叉树的依据

    ##### 7.7.1森林和二叉树的对应关系

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_213202.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-24_213446.jpg)

    > 由二叉树的兄弟表示法，链表表示法（将兄弟连成一个横向，**左下侧是孩子，右下侧是兄弟**）
    >
    > - 二叉树的根节点复制成第一棵树的根节点，形成一个只有左子树的二叉树，下一个树的做成该二叉树的右子树，

    > 二叉树转为森林
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-25_191653.jpg)

    ### 7.7 树和森林的遍历

    - 树的遍历：三条搜索路径，每个节点都要访问，每个节点只访问一次

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-25_192044.jpg)

     ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-25_192512.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-25_192744.jpg)

    - 树的先序 访问：先访问树的根节点，然后访问在根节点下的森林，然后先访问其中的第一棵树，使用先序遍历，访问完了，将下一棵树，也是这样进行访问的

    - ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-25_193336.jpg)

    - 树和森林的遍历

      1. 后序遍历和中序遍历是相同的，是一样的

      > 都是先访问第一棵树的并该树进行后根序遍历
      >
      > 这个地方将访问完A的时候访问左侧第一个树，并其模仿为二叉树的中序遍历，（因为是将EF看作为截断看作森林为B的左子树，B为根节点，剩余的看作为B的右节点，是这样的）
      >
      > 
      >
      > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-25_200924.jpg)
      >
      > 求取二叉树的深度，后序遍历，取最大，再+1
      >
      > 
      >
      > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-25_202858.jpg)
      >
      > - h1 是左子树森林森林，h2是右子树森林的深度
      >
      > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-25_203832.jpg)

      输出所有从根节点到叶子节点的路径（需要栈）

      ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-25_210753.jpg)

      ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-25_211336.jpg)

      ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-25_212328.jpg)

      - 因为树也可以用二叉树表示，所以这个路径是可以用于二叉树的   **【不对】**   因为二叉树表示叶子结点不是真正树的叶子结点

      > 如何通过二叉树来看树的叶子结点
      >
      > 二叉树的左子树空就是树的叶子结点

      - **遍历树的路径的时候，使用二叉链表表示的的方法就应该（上图）遍历完傻瓜的左子树时候开始退栈，遍历b的右子树的时候，就应该将b也弹出栈**  C G I 的右子树也如此

      这是对森林的遍历树结点 

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-25_213727.jpg)

    

    建树的存储结构算法：

      ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-25_215509.jpg)

    - 左侧为父母节点，右侧为当前节点，按照层次结构从左往右

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_190124.jpg)

    - 右下角是是一个队列盛放创建的已经创建结点，创建的结点进行保存

    先按层次遍历，创建结点

    - ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_184745.jpg)
    - ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_185013.jpg)

    ### 7.8哈夫曼树和哈夫曼编码

    ##### 最优树（哈夫曼树）的定义

    - 结点的路径长度定义：从根结点到该节点的路径上分支的数目
    - 树的路径长度：树中的每一个结点的路径长度之和
    - 树的带权路径长度：书中所有叶子节点带权路径长度之和

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_194151.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_194327.jpg)

    ##### 如何构造最优树

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_195246.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_195335.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_195407.jpg)

    ##### 前缀编码

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_195443.jpg)

    - 等长编码  A 00  B 01 C10 D 11  
    - 不等长编码：

    00 01 11 10 01 10 00   这是适合等长编码，器中每一个编码出现的概率是相同的

    哈夫曼 = 最优二叉树

    ### 8 图

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-30_193936.jpg)

    #### 8.1 抽象数据类型图的定义

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_201430.jpg)

    - 图上任何一个点都可以看做为顶点
    - 彼此之间地位是相等的

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_201658.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_201828.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_201912.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_202102.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_202252.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_202449.jpg)

    - 树的度为：子树的个数

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_202545.jpg)

    - **简单路径：**从节点A到结点B的路径上所经过的结点不会重复出现
    - **回路（简单回路）**： 若A= B的话

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_202930.jpg)

    - **连通图**：图中任意两个结点之间都有路径相通
    - **连通分量**：若**无向图**为**非连通图**，则途中各个极大联通子图称作此图的连通分量
    - **强连通图**：**有向图**中任意两个结点存在一条有向路径
    - **强连通分量**：是**有向图**的连通分量

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_203632.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_204344.jpg)

    - 创建一个图，要给出图的顶点的集合，和弧的集合

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_204635.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_204754.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_205023.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_205130.jpg)

    

    #### 8.2图的存储表示

    1. 图的数组存储表示

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_205351.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_205624.jpg)

    2. 图的邻接表存储表示

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_205913.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_210052.jpg)

    - 无向图：表示的边是重复的
    - 逆向邻接表

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_211308.jpg)

    - 在正向邻接表中能找到他指向别的顶点的的弧，在逆向邻接表中，能找指向它的弧，这样我希望你能够同时得到这两个 功能

    3. 有向图的十字链表

      结点：  数据域（1）  指针域  |  数据域（2） 指针域

    数据域为1的指针域指向弧指向它的结点的地址

    数据域2 为指针域为它指向别的弧的节点的地址

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_213332.jpg)

    - 横向为指向别的，竖的为别的指向它的

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_212957.jpg)

    4. 无向图的**邻接表多重表**存储表示

    - 将无向图多余的边用一条表示

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_214415.jpg)

    #### 8.3图的遍历

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_214829.jpg)

    - 深度优先遍历

    > 如果该图是连通图的话肯定能够遍历整个图
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-26_215200.jpg)

    - 与树的先根遍历是一样的，但与树不相同的是，图的深度遍历有重复结点出现
    - DFS与树的不相同 检查邻接点是否被访问过，在每个节点上做上是否访问过的标志
    - 连通图

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_185805.jpg)

    - 非连通图

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_190350.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_190816.jpg)

    - 就是访问每一个开始的点的邻接点
    - 通过深度优先遍历生成的右上的树称为深度优先生成树

    

    - 广度优先遍历

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_191348.jpg)

    - 先访问一个结点，就把该结点的所有的邻接点访问完，然后就按照上面访问邻接点的顺序进行访问相应点的邻接点
    - 就是按照到访问最初访问节点的路径长短来进行访问，先访问路径为1的再访问路径为2的，就是到达最初访问节点的邻接点的路径为1的

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_192542.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_193339.jpg)

    

    - 题例：
    - 深度和广度都可以找到路径

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_202710.jpg)

    - 广度可以找到最短的一条路径
    - 找最短路径：改进广度优先遍历，将广度优先遍历的队列进行改进，如下图，加上被指向的邻接点，到指向它的指针，这样就可以找到，是谁遍历到他的，这样可以找到源头，方便找最短路径
    - 队列在树的创建时候用到，使用树的二叉树表示的时候，加上一个表

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_203655.jpg)

    - 第一次使用双向链表，而且是跳跃的

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_204321.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_204442.jpg)

    #### 8.4最小生成树

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_213132.jpg)

    - 最小生成树是作用在：**无向网**

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_204743.jpg)

    - 构成的是一个连同的无环的网
    - 算法一：普利姆算法：

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_205442.jpg)

    > 从第一个顶点中从可选的边中选一个权值最小的边
    >
    > 是遍历邻接矩阵的
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_210626.jpg)
    >
    > 在主键生成树上加节点，是每一次加进去连通的权值最小

    算法二：克鲁斯卡尔算法

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_212131.jpg)

    - 点都先罗列出来，选取边选取权值最小的可选边，然后判断是否产生回路
    - 图上的权值进行排队是要先进行排序的

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_212540.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_212638.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-27_212308.jpg)

    #### 8.5重（双）连通图和关节点

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-28_195255.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-28_195421.jpg)

    - 没有关节点的连通图为双连通图
    - 深度优先遍历

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-28_195815.jpg)

    - 如果生出树有两个边证明，访问子树数据只能通过这个结点
    - 回边的作用，如果没有回边，没有直接连接到指定节点，则该结点不能直接与指定节点相连   例如 e可以与c相连，但不可以与a直接相连

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-28_200905.jpg)

    - 这是看生成树根是不是根节点

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-28_201014.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-28_201609.jpg)

    

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-28_203031.jpg)

    - 原始排序  未加回边

    从第一个没有孩子节点的生成树往根节点进行遍历，求取相关值，做成为 

    该节点low值 =（ 求取本身的访问次序，子树根low值，与该结点有回边相连的的次序值（没有回边的默认先序过来的次序为回边值））取最小

    

    举例子  low（e） = { 5，0，3  }   就是三了

    low（d） = {4，3，3} 就是三了

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-28_204055.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-28_204459.jpg)

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-28_204736.jpg)

    #### 8.6两点之间的最短路径问题

    - 从原点到其余各点的最短路径

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-28_205249.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-28_205423.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-28_205631.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-28_210414.jpg)

    

    - 问题二   **每一对顶点间最短路径：**

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_184749.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_185036.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_185114.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_190845.jpg)

    - 是通过逐渐在原先搭配中，添加中介，按照节点循序，例如

    B->A 没有路径，当中介增加到C的时候，就有了，因为存在B->C和C->A所以就像加，这样相加的结果比之前原先就有的结果小，就会替换，因为这个求图的每一个节点到其他结点最短路径，需要权值邻接矩阵，路线邻接矩阵

    #### 8.7拓扑排序

    - 解决有向图

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_191056.jpg)

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_191246.jpg)

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_191504.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_195858.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_200025.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_192306.jpg)

    - 求取有向图图中入度为0的结点

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_192437.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_192535.jpg)

    #### 8.8关键路径

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_201016.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_201211.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_201312.jpg)

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_201953.jpg)

    - 关键路径是在拓扑排序上进行的

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_202830.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_203352.jpg)

    - 最早开始时间（ee）和最晚开始时间（el）**相同**的就是**关键事件**
    - ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-29_203740.jpg)

    

    ### 9 查找表

    - 查找表是由同一类型的数据元素（记录）构成的集合

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_201011.jpg)

    - 进行的操作不同分为静态查找表（只进行前两种的）动态查找表（只进行后两种的） 
    - 关键字   主码  非主码（次关键字）
    - 查找是查找的主关键字
    - 动态查找：对找不到的数据，进行插入，查找成功的形况下进行删除
    - 该章介绍查找表的表示方法，以及如何在某种表示方法下如何进行的，以及再给中查找表的情况下如何插入删除

    #### 9.1 静态查找表

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_195134.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_195225.jpg)

    ##### 顺序存储结构：

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_195346.jpg)

    ###### 1.顺序查找表

    - ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_195559.jpg)
    - 将0位置值为空（不用）

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_195802.jpg)

    O(n)

    - **k<=L.length 是占据时间复杂度的一半，但是不能没有，想办法将之消除（将数组从后往前查找，在o好索引处加上一个要查找的数据的关键字，这样就不会出界，只是最后返回式判断如果索引值是0的话，就是不存在）**

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_200434.jpg)

    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_200537.jpg)
    >
    > 如果表长是10，p就是1/10，C是的几个查找到的
    >
    > - 等概率
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_200946.jpg)
    >
    > - 不等概率
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_201620.jpg)

    - 表长较小

    ###### 2. 有序查找表

    - 表长比较大

    ###### 折半查找

    - 找**中间**为索引最小加索引最大/2
    - 若中件索引表示的数比要找的数大，就将上指针知道中件位置减一，在找中间
    - 若下指针大于上指针，则跳出循环

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_202726.jpg)

    - 分析折半查找的平均长度

    > 查看折半查找的每一个查找结果，将概率填写上，然后根据查找为1次的放在第一层上，为2的就放在第二层上。。。。。
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_203516.jpg)
    >
    > 下面空白的是查找不成功的
    >
    > （1 * 1 +2 * 2+4 * 3+4 * 4  ）/11就是该表有序的折半查找的平均查找长度

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_204214.jpg)

    ###### 3. 静态查找树表

    不能够将查找概率最大的放在中间，所以

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_204759.jpg)

    - 还是在有序的情况下：根据概率不同选择一个分界点

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_205055.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_205535.jpg)

    - 这里构造次优 二叉树的构造方法

    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_205948.jpg)
    >
    > 1. ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_210101.jpg)
    >
    > 选一个根节点，满足左边权值和与右边的权值和，差的绝对值取最小，黛儿塔p就是权值差
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_210917.jpg)
    >
    > 2. 权值差最小的是在第F(称为跟结点)，则就分成两个，将A-E分成一个，将G-k分成一个，在进行权值差的运算 取最 小
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_211311.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_211535.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_211756.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_212010.jpg)
    >
    > - 推导出一个计算公式：sw =将概率从左到右，依次加起来，上图公式pi = | (sw_h +sw_l-i)- sw_i-sw_i-1|
    >
    > h 是它的上界，l 是他的下界
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_213259.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_213408.jpg)

    ###### 4. 索引顺序表

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_213635.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_213755.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_213834.jpg)

    - 建一个有序索引，存取某个区间的值
    - ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_214239.jpg)
    - ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-03_214430.jpg)

    #### 9.2 动态查找表

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_180556.jpg)

    - 数据元素同属于一个集合

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_180641.jpg)

    - 构造静态查找表是之前就生成好的，但是动态查找表是构造一**个空的**

    ###### 动态查找树表

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_181745.jpg)

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_181826.jpg)

    ###### 1.二叉排序树（二叉查找树）

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_182229.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_182402.jpg)

    - 若果左子树的根节点小于根节点，并不可能是二叉搜索树，因为左根节点的右子树大于左根节点，就有可能大于根节点，**所以要求整个左子树都要小于根节点**

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_183240.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_183325.jpg)

    - 当前查找不存在时，p指针会存取要查的但没找到的地址，创建一个新的结点，将该数据存储进去，将指针域存取好

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_184319.jpg)

    - 二叉排序树（二叉搜索树）的删除：

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_184941.jpg)

    - 删除的时叶子节点：中间没有断开，还是二叉排序树，只要把双亲的结点域变为空，释放该叶子节点即可。
    - 删除右子树（只有右子树），但是有一串都是只有右子树的，

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_185343.jpg)

    例如删除40，只要剩下的结点还在右子树上即可/只有左子树同样

    - 删除的既有左子树又有右子树

    > **这个二叉排序树是通过一个有序表得来的，所以删除一个既有左子树又有右子树的结点，所以可以找他的前去和后继来顶替**
    >
    > 前驱：是左子树的最右下孩子叶子节点

       ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_190727.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_190811.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_190833.jpg)

     性能：

     ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_191254.jpg)

    - **插入关键子的顺序就会有ASL很大的不同**

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_191504.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_191657.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_191754.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_192229.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_193421.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_193504.jpg)

    

    ###### 2.二叉平衡树

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_193915.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_194050.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_194239.jpg)

    - 引入结点平衡因子（左子树的深度- 右子树的深度）

    1. 现在插入关键字 =12的结点，在24结点的左子树上插入，没有影响

    ​       整个二叉树没有失去平衡

    2. 现在插入结点48，插入到49的左节点上，会先使61结点变得不平衡再是88，然后是38，而61是最小不平衡子树，让他平衡了，整个平衡二叉树就平衡了，进行**右旋转** ，让61变成49的右节点，49称为88的左节点

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_200233.jpg)

    在该平衡车二叉树上插入结点55，最小不平衡树为 88

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_201335.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_201358.jpg)

    - 平衡二叉树是在平衡查找树上查找到的
    - 当插入数据的时候，查看插入进去检查是否平衡，不平衡的话就进行旋转

    性能：

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_203051.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_203547.jpg)

    ------

    下面的三种树是作为文件的索引，存储在外存上的

    ###### 3. B - 树

    - 与二叉排序树不一样，只有两个子树
    - 1. b树有多个子树
    - 2. 平衡的

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_203901.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_204050.jpg)

    > 这儿的子树都是以区间划分的，注意
    >
    > 负无穷- 24
    >
    > 24-55 、55-74、74-正无穷
    >
    > 叶子节点是1等下面的空指针

    6的所指的子树的结点都小于6

    11所指的结点的子树的值都大于6

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_205443.jpg)

    m阶就是有m个子树，m-1个根节点

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_211317.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-04_211509.jpg)

    五阶b树最多是五棵子树

    如果子树超过，就会子树分裂

    下面的b树使五届的，现在要进行子树分裂

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_201918.jpg)

    在该满的节点上，取出m/2的上界，将42移到其父节点上，将43、44进行改变

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_202304.jpg)

    b树的删除：

    m/2为下届，每个节点都删除的时候需要判断

    删除当前结点，不能删，借右儿子

    - 删除45

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_202921.jpg)

    先进行45与47的交换（将47替换掉45）

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_203028.jpg)

    然后再在子节点上删除47

    删除2（借兄弟，删除当前结点，与父节点都不可以删除）：

    - 删除44![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_203313.jpg)
    - 先删除44，想右节点兄弟借，将47移下来，将48移上去

    删除3（当删除当前节点，不行，借父节点不行，右兄弟，也不可以）![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_203851.jpg)

    删除40

    （1）严：将该结点剩余的41包括父节点该系42，一起移到，右兄弟上

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_204229.jpg)

    （2）我觉得可以将42直接移到40位置上去【不可以】

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_204849.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_205522.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_205547.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_205605.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_205623.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_205655.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_205912.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_210244.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_213022.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_212514.jpg)

    ###### 4. B+ 树

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_212834.jpg)

     ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_213136.jpg)

    在B+树中所有的结点都会在叶子节点上出现

    - 但从下面看就是一个单链表
    - 父母结点，分别也表示该单链表中最大的值

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-05_213626.jpg)

    

    ###### 5. 键树

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_194745.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_195009.jpg)

    - 树的深度与关键字长度有关

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_195246.jpg)

    - 第一种是树的兄弟表示（适合关键字少），是树的二叉树的表示方法
    - ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_195611.jpg)
    - 多重关联表，使用27个加结束符

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_195846.jpg)

    - 将最后一个压缩为叶子结点，存放关键字和信息下一个指针域

    #### 9.3 哈希表

    ##### 1. 哈希表是什么？

      ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_200808.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_200830.jpg)

    - 希望平均查找长度为0，不经过比较，有目的的获取准确信息，事先知道含关键字在什么位置，该记录与关键字存在确定的关系

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_201232.jpg)

    - 动态查找表：表长不确定

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_201513.jpg)

    - 哈希函数：生成一种联系-关键字和记录在表中的位置
    - **哈希表是基于哈希函数建立的一种查找表**

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_201802.jpg)

    对第一个字母进行哈希函数映射，是第一个（字母位序+1）/2

    （26+1）/2 = 13    存储是0-13，表长是14 是可以

    比如第一个字母是Dei中的D所以D：（4+1）/2是（下取整）2

    上面的f就是是哈希函数

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_202648.jpg)

    > 哈希函数就是将记录上的某一个属性映射到存储地址上，
    >
    > 如上面学生学号问题
    >
    > 哈希函数是一个压缩映象，上面将26个字母压缩到长度14为顺序表中

    下面就有问题，万一设置的哈希函数，表长对不上关键子对应的位置，会出现冲突（同义词冲突），

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_203022.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_203355.jpg)

    

    ##### 2.哈希函数的构造方法

    - 如何选择一个好的哈希函数
    - 1. **非数字关键字**需要先将对其进行**数字化处理**

    ###### 1.直接定址法

    哈希函数为关键字的线性函数

    - **仅限于地址集合的大小 = 关键字集合的大小**
    - 但是动态查找表就是限定于这么大

    优点- 没有冲突

    ###### 2. 数 字分析法

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_204251.jpg)

    - 假设关键字长为5位，存储的记录地址是3位
    - 分析关键字的趋势

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_204548.jpg)

    ###### 3.平方取中

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_204618.jpg)

    ###### 4.折叠法

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_204711.jpg)

    ###### 5.除留余数法

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_204841.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_204955.jpg)

    - p可以是m表长，可以小于m，但不可以大于m

    ###### 6.随机数法

    

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_205148.jpg)

    ##### 3.处理冲突的方法

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_205225.jpg)

    ###### 1. 开放定址法

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_205402.jpg)

    - 第一对记录取哈希函数，取哈希地址，如果地址上没有记录，就把该记录，放在该位置上
    - 如果存在记录，就另找位置，加上一个增量值di，若果该地址是空的就放入
    - 有记录的话再找一个增量值，如果表不满的话，总会有一个位置的

    > 增量di的三种区法：
    >
    > 1. ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_205939.jpg)
    >
    > 就是位置有记录，就会直接找下一个位置（绕圈找）
    >
    > 2. ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_210138.jpg)
    > 3. ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_210206.jpg)
    >
    > ​       双哈希

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_212113.jpg)

    ###### 2.链地址法

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_212202.jpg)

    - 不会产生二次冲突

    ##### 4.哈希表的查找

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_212354.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_212646.jpg)

      ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_212916.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_213038.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_213159.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_213242.jpg)

    **求平均查找长度的时候，将第一看是否有记录，也会算一次**

    

    ##### 5.哈希表的删除操作

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_213722.jpg)

    不能简单地删除，会影响后面的查找

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_213829.jpg)

    > 将14在3中的位置上删除，现在我们要找11，11%11等于0索引，使用开放定址法中的线性再散列技术，查找+1找到
    >
    > 1索引但是在3位置是空的，我们不嫩给再往下找，所以映象随便删除映象查找

    - 特殊处理：要删除，并修改查找算法

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_215132.jpg)

    

    - 设计哈希函数

    ##### 6.对静态查找表。。

     ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_220104.jpg)

     

     ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_220308.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-06_220616.jpg)

    ### 10 排序

    #### 10.1 概述

    - 排序是什么？

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_195317.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_195453.jpg)

    

    - 内部排序和外部排序

    ​         内部排序，在排序的时候不去访问外部空间

    - 内部排序方法的分类

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_195735.jpg)

    - 一趟排序：将无序序列中一个或者几个记录合并到有序序列中，是的有序序列长度增长

    如何扩大一趟排序有序序列长度，划分排序种类

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_195949.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_200032.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_200051.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_200132.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_200202.jpg)

    #### 10.2 插入排序

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_200416.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_200527.jpg)

    ###### 直接插入排序

    - 顺序查找要插入的位置

      ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_200807.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_201106.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_201136.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_201344.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_201647.jpg)

    最好的和最坏的的平方还是 O（n^2）

    ###### 折半插入排序

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_201943.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_202001.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_202109.jpg)

    - 折半查找插入位置
    - 后移
    - 插入

    ###### 表插入排序

    - 减少排序中的移动次数

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_202330.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_202540.jpg)

    将关键字存入一个顺序表中，索引0指的是该表中关键字（记录）最小的，而每一个关键字在下面所指的次小于它的关键字的索引

    > k是当前比较的关键字，j是它的当前比较的前驱、
    >
    > 因为当前表是指示存储比该关键子小的指针，当你比较，该指针当前正好大于i指示的关键字，所以要修改k所指的指针值，就是如次防止再次查找一边
    >
    > 

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_203741.jpg)

    - 拍好相对索引，然后根据索引来调整位置

      ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_203934.jpg)

      - i指针（从索引为1的，逐步加1）指的与p指针值得进行交换，q指针指向i的下一个数据
      - 换完之后将i的指针要换成p指针所在的索引
      - 再下一次就是i与q进行比较

      > i从索引为1的地址依次往后排序，p指针指示的是第一个索引为0指示的地址，q指示的是p指示的下一个第一值，分别是，i指示的最小关键字要放的位置，p指示的是最小的关键字，而q指示的第二小的关键字位置，
      >
      > 1. 首先将i指示的位置与最小关键字p指示的位置，进行叫交换，并将换到i位置的最小的关键字的next指值指向刚刚交换的位置，就是p指针指示的位置
      > 2. i后移，比较第二个，现在是i是到了关键字第二小的位置，正是q所指的关键字，现在将p移到q指的的记录的next指针，并进行i与q交换，重复上面操作

      ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_210552.jpg)

      ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_212857.jpg)

      ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_212925.jpg)

    

    ###### 希尔排序（缩小增量排序）

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_213335.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_213430.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_214327.jpg)

    增量为5（这是第一躺）

    - 就是第一个第六个还有第十一个，这是一组进行直接插入排序，这三个称为了有序序列
    - 第二个第七个进行排序，大小比较好了，放回第二个还有第7个位置

    增量为3（第二趟）

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_214811.jpg)

    最后一趟

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_214840.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_214953.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_215038.jpg)

    #### 10.3快速排序（交换排序）

    ###### 冒泡排序

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_215451.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_215531.jpg)

    - 每一次都是与后继比较
    - 结束的条件：**最后一趟没有进行交换**

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_215811.jpg)

    

    ###### 一趟快速排序

    - 找枢轴

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_215912.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_220112.jpg)

    - 设两个指针一个指导前面，一个指到后面

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_220250.jpg)

    - 思想，将高指针逐渐下移，低指针上移，上指针如果比枢值小，就暂停，直到下指针找到比枢值大的，然后进行交换
    - 思想是将枢纽现已出来，找到你个比它大的就移到枢纽原先位置，前后指针来回比较

    ###### 快速排序

    对一次快速排序进行递归操作

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_220959.jpg)

    - 快排的时间分析

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_221114.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_221201.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-07_221307.jpg)

    

    #### 10.4堆排序（选择类）

    ###### 简单选择排序

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_201244.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_201330.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_201440.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_201456.jpg)

    - 不管顺序如何，比较次数相同
    - 记录移动次数最小

    O(n^2)

    ###### 堆排序

    在输出堆顶最小值之后，使得剩余n-1个元素的序列又建成一个堆，则得到n个元素的次小值，如此反复操作，便能得到有序序列，这一过程称为堆排序

    - 什么是堆？

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_202159.jpg)

    - r1一定是该数列中最大的，或者最小的

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_202329.jpg)

    上列是堆，下列是为了直观

    与查找树不同的是，没有左小根，右大根这种现象，他的根都是大于根节点

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_202904.jpg)

    - 将他变成大顶堆，前五个是由孩子结点的，因为一共10个，i的孩子是2i和2i+1，所以第五个结点是有一个孩子的

    

    > 怎样建堆（如何调整堆）
    > 建堆的步骤：
    >
    > 从最后一个非终端结点开始往前逐步调整，让每个双亲大于（或小于）子女，直到根节点为止。
    >
    > 注意：终端结点（即叶子）没有任何子女，无需单独调整。
    >
    > 建堆的具体做法：
    >
    > （1）将**原始序列转**换成完全二叉树。
    >
    > （2）从序号最大的非叶子节点开始遍历，左右孩子中有比它大的，交换该节点和叶子的位置。
    >
    > （3）父节点和较大的孩子节点交换后，新的父节点是稳定的，但是新的孩子节点可能不满足大顶堆规则，而另一边的孩子不会受影响。
    >
    > （4）继续对新孩子进行调整判断，直至新孩子满足规则，或者没有新孩子为止。

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_205016.jpg)

    如何将大顶树排序的数组，转化为从小到大的序列

    - 先将98与12 进行交换，则最大的进入不管区，因为12在最前面不满足，大顶堆排序，所以与进行**筛选**，进行一次大顶数排序，重新生成大顶树，然后再与最后一个12进行交换，然后12在最前面不服和大顶树的要求，在进行一次**筛选**，不使81、98参与
    - 关键在于**筛选**，即对剩下的数据进行大顶树排序

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_205834.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_205906.jpg)

    筛选算法

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_205929.jpg)

    - 如何筛选呢（如何建造大顶树呢）

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_210402.jpg)

    - 观察，多出来一个空的叶子节点
    - 98移除、将最小12的移到树顶

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_210515.jpg)

    1. 12开始与左右子树的最大值进行交换 （左子树与右子树进行比价） 及81移上取与12交换

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_210732.jpg)

    2. 在进行检查81原先位置的左右子树，是否大于12，和左右子树谁大问题，决定谁落在81原先位置，显然73

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_210927.jpg)

    3. 再决定73原先位置，同上，最后12落在叶子节点上，则一次筛选![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_211023.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_211205.jpg)

    > 会一直是12吗？不会的，因为要进行大顶树排序，而且每一次取值交换的时候，最大的值都是要到数组最后，也就是分层遍历，从左到右的顺序交换
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_211252.jpg)
    >
    > 

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_211837.jpg)

    > 如何建立大顶堆（形象化）
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_212026.jpg)
    >
    > 判断是不是大顶树，判断有子树的第一个结点进行检查（n/2）
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_212503.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_212536.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_212607.jpg)
    >
    > - 也就是从n/2个结点看起，是一个有子树的小树，进行筛选操作，使之称为大顶树，然后n/2- 1慢慢往前的一个循环的筛选操作
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_212848.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_213037.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_213240.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_213326.jpg)

    #### 10.5归并排序

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_213404.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_213438.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_213513.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_213610.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_213835.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_213926.jpg)

     ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_214227.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_214408.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_214446.jpg)

    #### 10.6基数排序（多关键字）

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_214810.jpg)

    - 两个串的大小比较，字符艾克斯码比较

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_214857.jpg)

     ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_215121.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_215214.jpg)

    - MSD分成子序列

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_220011.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-08_215912.jpg)

    班号排序的时候不需要管系号和学号（这样下来一个系一个班学号不同的能排好序吗）对学号拍完了k2之后，进行k1排序的时候，1.2.15与3.2.30需不能打乱顺序，这种排序叫做**稳定排序**

    不需要分开排序

    ###### 链式基数排序：

    - 借助多关键字排序的思想来来实现但关键字排序的算法；
    - 链式基数排序

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_194326.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_194518.jpg)

    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_194935.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_195033.jpg)
    >
    > 使用队列来
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_195222.jpg)
    >
    > - 第二次就是按照十位进行排序，这是稳定排序，第一次个位排序是不变的
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_195412.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_195446.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_200423.jpg)
    >
    > ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_200542.jpg)
    >
    > - 时间复杂度与记录位数成正比，与个数成正比

    #### 10.7 各种排序方法的综合比较

    - 基本有序采用直接插入排序
    - 基本有序不才用快速排序

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_201542.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_201930.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_202053.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_202137.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_202239.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_202434.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_202415.jpg)

    - 稳定性 是指两个相同的数据，47，如果依次排序后，还是紫的在前，蓝的在后这是稳定的，反之就是不稳定的

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_202700.jpg)

    - 跳跃式来实现排序就是不稳定的

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_202954.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_203206.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_203319.jpg)

    #### 10.8 外部排序

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_203414.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_203502.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_203602.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_203702.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_203904.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_204000.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_204040.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_204125.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-09_204221.jpg)

    

    ## 真题

    #### 线性类题

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_191000.jpg)

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_191025.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_191301.jpg)

    

    

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_192534.jpg)

    - 从空栈到空栈，
    - 考虑栈满的化考虑到如何实现的问题
    - ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_192726.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_192510.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_193055.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_193419.jpg)

    - 模拟栈

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_194337.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_194517.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_194640.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_195855.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_200819.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_201331.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_201517.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_201747.jpg)

    - 思路：可以通过该字符串的每一个去掉首字母后进行next函数运算，当取到next就函数值最长的就是，14个字符的话，要进行13次next函数计算，计算出，最长的next函数组中最大的数字

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_203200.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-10-21_204222.jpg)

    #### 非线性类

    - 遍历时所有非线性结构（二叉树，树，图，广义表）的操作基础
    - 不同的应用需要不同的搜索路径

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-01_201501.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-01_201641.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-01_202224.jpg)

    - （上面的）使用的先序

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-01_202545.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-01_202713.jpg)

    - disp是删除该子树所有孩子，包括释放

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-01_203255.jpg)

    - 如果子树根节点的算术运算符的优先级低于跟的运算符的优先级，则需要加括号

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-01_203559.jpg)

    - precede函数是判断运算符的优先级

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_192106.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_192230.jpg)

     

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_192915.jpg)

    - 非递归

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_194030.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_194225.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_194328.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_194719.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_195032.jpg)

    - 上面错误有错

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_195318.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_195517.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_195650.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_200217.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_200314.jpg)

    ![](https://raw.githubusercontent.com/eshmarry/dong_markdown/master/img/2019-11-02_200450.jpg)

    