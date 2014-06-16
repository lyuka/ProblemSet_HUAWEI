#华为历年机试题集合
----
##2014
[code](http://blog.csdn.net/hackbuteer1/article/details/11132567)
###题1（60分）
通过键盘输入一串小写字母（a~z）组成的字符串。请编写一个字符串过滤程序，若字符串中出现多个相同的字符，将非首次出现的字符过滤掉。比如字符串`abacacde`过滤结果为`abcde`。

要求实现函数：

```c
void stringFilter(const char * pInputStr, long lInputLen, char * pOutputStr)
```

【输入】pInputStr：输入字符串  
      
           lInputLen：输入字符串长度  
           
【输出】pOutputStr：输出字符串，空间已经开辟好，与输入字符串等长

【注意】只需要完成该函数功能算法，中间不需要有任何IO的输入输出

>示例  
>输入：`deefd`        输出：`def`  
>输入：`afafafaf`     输出：`af`  
>输入：`pppppppp`     输出：`p`

---
###题2（40分）：
通过键盘输入一串小写字母(a~z)组成的字符串。请编写一个字符串压缩程序，将字符串中连续出席的重复字母进行压缩，并输出压缩后的字符串。  
压缩规则：  
1. 仅压缩连续重复出现的字符。比如字符串`abcbc`由于无连续重复字符，压缩后的字符串还是`abcbc`  
2. 压缩字段的格式为"字符重复的次数+字符"。例如：字符串`xxxyyyyyyz`压缩后就成为`3x6yz`

要求实现函数：
```c 
void stringZip(const char * pInputStr, long lInputLen, char * pOutputStr);
```

【输入】pInputStr：输入字符串 
 
           lInputLen：输入字符串长度         
【输出】pOutputStr：输出字符串，空间已经开辟好，与输入字符串等长；

【注意】只需要完成该函数功能算法，中间不需要有任何IO的输入输出

>示例   
输入：`cccddecc`   输出：`3c2de2c`  
输入：`adef`     输出：`adef`  
输入：`pppppppp` 输出：`8p` 

---
###题3（50分）
通过键盘输入100以内正整数的加、减运算式，请编写一个程序输出运算结果字符串。
输入字符串的格式为：“操作数1 运算符 操作数2”，“操作数”与“运算符”之间以一个空格隔开。

补充说明：  
1. 操作数为正整数，不需要考虑计算结果溢出的情况.  
2. 若输入算式格式错误，输出结果为“0”。

要求实现函数：
```c 
void arithmetic(const char * pInputStr, long lInputLen, char * pOutputStr);
```

【输入】 pInputStr：输入字符串  

           lInputLen：输入字符串长度         
【输出】 pOutputStr：输出字符串，空间已经开辟好，与输入字符串等长；

【注意】只需要完成该函数功能算法，中间不需要有任何IO的输入输出

>示例   
输入：`4 + 7`  输出：`11`  
输入：`4 - 7`  输出：`-3`  
输入：`9 ++ 7`  输出：`0` 注：格式错误   
---

##2013
[code](http://blog.csdn.net/hackbuteer1/article/details/11150519)
###题1 子串分离
通过键盘输入任意一个字符串序列，字符串可能包含多个子串，子串以空格分隔。请编写一个程序，自动分离出各个子串，并使用`,`将其分隔，并且在最后也补充一个`,`并将子串存储。 
如果输入`abc def gh i        d`，结果将是`abc,def,gh,i,d,` 
 
要求实现函数：
```c 
void DivideString(const char * pInputStr, long lInputLen, char * pOutputStr); 
```

【输入】pInputStr：输入字符串  

          lInputLen：输入字符串长度                   
【输出】pOutputStr：输出字符串，空间已经开辟好，与输入字符串等长； 

【注意】只需要完成该函数功能算法，中间不需要有任何IO 的输入输出 

>示例     
输入：`abc def gh i        d`   
输出：`abc,def,gh,i,d,`
---

###题2 逆序链表输出     
将输入的一个单向链表，逆序后输出链表中的值。链表定义如下： 
```c
typedef struct tagListNode 
{ 
      int value; 
      struct tagListNode *next; 
}ListNode; 
```

要求实现函数：
```c   
void converse(ListNode **head);
```
 
【输入】head：链表头节点，空间已经开辟好  
【输出】head：逆序后的链表头节点  
【返回】无 

【注意】只需要完成该函数功能算法，中间不需要有任何IO 的输入输出 

---
## 2012
[code](http://blog.csdn.net/hackbuteer1/article/details/11161557)
### 题1
选秀节目打分，分为专家评委和大众评委，`score[]`数组里面存储每个评委打的分数，`judge_type[]`里存储与`score[]`数组对应的评委类别，`judge_type[i] == 1`，表示专家评委，`judge_type[i] == 2`，表示大众评委，`n`表示评委总数。打分规则如下：专家评委和大众评委的分数先分别取一个平均分（平均分取整），然后，总分 = 专家评委平均分  * 0.6 + 大众评委 * 0.4，总分取整。如果没有大众评委，则 总分 = 专家评委平均分，总分取整。函数最终返回选手得分。  
函数接口
```c
int cal_score(int score[], int judge_type[], int n)
``` 
---
###题2
给定一个数组`input[]`，如果数组长度n为奇数，则将数组中最大的元素放到`output[]`数组最中间的位置，如果数组长度`n`为偶数，则将数组中最大的元素放到`output[]`数组中间两个位置偏右的那个位置上，然后再按从大到小的顺序，依次在第一个位置的两边，按照一左一右的顺序，依次存放剩下的数。
例如：  
>input[] = {3, 6, 1, 9, 7}   output[] = {3, 7, 9, 6, 1};  
>input[] = {3, 6, 1, 9, 7, 8}    output[] = {1, 6, 8, 9, 7, 3}

函数接口   
```c
void sort(int input[], int n, int output[])
```
---
###题3 操作系统任务调度问题。
操作系统任务分为系统任务和用户任务两种。其中，系统任务的优先级 `< 50`，用户任务的优先级 `>= 50`且 `<= 255`。优先级大于`255`的为非法任务，应予以剔除。现有一任务队列`task[]`，长度为`n`，`task`中的元素值表示任务的优先级，数值越小，优先级越高。函数`scheduler`实现如下功能，将`task[]`中的任务按照系统任务、用户任务依次存放到 `system_task[]`数组和`user_task[]`数组中（数组中元素的值是任务在`task[]`数组中的下标），并且优先级高的任务排在前面，优先级相同的任务按照入队顺序排列（即先入队的任务排在前面），数组元素为`-1`表示结束。 例如：
>task[] = {0, 30, 155, 1, 80, 300, 170, 40, 99}    
>system_task[] = {0, 3, 1, 7, -1}    
>user_task[] = {4, 8, 2, 6, -1}
     
函数接口   
```c
void scheduler(int task[], int n, int system_task[], int user_task[])
```