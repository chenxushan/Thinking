## 数组

```java
//Arrays.fill(dp,0);
int[][]A={
    {4,3,4,5,3},
    {2,7,3,8,4},
    {1,7,6,5,2},
    {8,4,9,5,5}
};

int a = 0;
int b = 1;
int[] tmp = new int[]{a, b};

//        public static <T> T[] copyOfRange(T[] original,
//        int from,
//        int to)

//System.arraycopy(T[] source, int sourcePos,T[] dest_arr, int destPos, int len)

//System.out.println(Arrays.toString(arr));
//这里要注意：不能直接 arr.toString()
int[] arr=new int[6];
int length = arr.length;
int[] y= new int[]{1,2,3,4,5};
int [][] intA={{1,2},{2,3},{3,4,5}};
int [][] intC= new int[3][5];

int [][]intB=new int[3][];
intB[0]=new int[3];  //3
intB[1]=new int[]{1,2,3,4};  //3
intB[2]=new int[2];  //2
System.out.println(intB[1]);//[I@156643d4
System.out.println(intB[1][1]);//2

//二维数组
int [] intD[] ={{1,2},{2,3,4},{3,4,5,6}};
//(1)普通for循环
for(int i=0;i<intD.length;i++){ //0,1,2
    for(int j=0;j<intD[i].length;j++){ //每一个一维数组的长度
        System.out.print(intD[i][j]+"\t");
    }
    System.out.println();
}
//(2)加强for循环
System.out.println("\n=========================");
for(int[] arr1:intA){  //int[]二维数组中元素的类型, arr迭代变量, intA二维组的名称
    for(int i:arr1){ //int，一维数组中元素的类型，i,迭代变量,arr，一维数组的名称
        System.out.print(i+"\t");
    }
    System.out.println();
}
```

#### 数组转换

```java
int[] array = new int[] {1, 2, 3};
List<int[]> intArray = Arrays.asList(array);
for (int[] arr:intArray) {
    System.out.println(Arrays.toString(arr));
}
// 二维数组
int[] arr=new int[6];
int length = arr.length;
int[] y= new int[]{1,2,3,4,5};
int [][] intA={{1,2},{2,3},{3,4,5}};
int [][] intC= new int[3][5];

System.out.println(Integer.MAX_VALUE);
System.out.println(Integer.MIN_VALUE);
int[] a = new int[]{3,2,6,4,8,2};
// int[] 转 List<Integer>
List<Integer> list1 = Arrays.stream(a).boxed().collect(Collectors.toList());
Arrays.sort(a);
// int[] 转 Integer[]
Integer[] integers1 = Arrays.stream(a).boxed().toArray(Integer[]::new);
System.out.println(Arrays.toString(integers1));
// List<Integer> 转 Integer[]
Integer[] integers2 = list1.toArray(new Integer[0]);
//  调用toArray。传入参数T[] a。这种用法是目前推荐的。
// List<String>转String[]也同理。
// List<Integer> 转 int[]
int[] arr1 = list1.stream().mapToInt(Integer::valueOf).toArray();
// 想要转换成int[]类型，就得先转成IntStream。
// 这里就通过mapToInt()把Stream<Integer>调用Integer::valueOf来转成IntStream
// 而IntStream中默认toArray()转成int[]。

// Integer[] 转 int[]
int[] arr2 = Arrays.stream(integers1).mapToInt(Integer::valueOf).toArray();
// 思路同上。先将Integer[]转成Stream<Integer>，再转成IntStream。

// Integer[] 转 List<Integer>
List<Integer> list2 = Arrays.asList(integers1);
// 最简单的方式。String[]转List<String>也同理。
// 同理
String[] strings1 = {"a", "b", "c"};
// String[] 转 List<String>
List<String> list3 = Arrays.asList(strings1);
"注意这里list3里面的元素直接是strings1里面的元素( list backed by the specified array)，换句话就是说：对strings1的修改，直接影响list3。"
// List<String> 转 String[]
String[] strings2 = list3.toArray(new String[0]);
"注意这里的strings2里面的元素不是list3里面的元素，换句话就是说：对list3中关于元素的修改，不会影响strings2。"
```
### 集合转换
因为List和Set都实现了Collection接口，且addAll(Collection<? extends E> c);方法，因此可以采用addAll()方法将List和Set互相转换；另外，List和Set也提供了Collection<? extends E> c作为参数的构造函数，因此通常采用构造函数的形式完成互相转化。

```java
//List转Set,list转set，可用于元素去重的场景
Set<String> set = new HashSet<>(list);
System.out.println("set: " + set);
//Set转List
List<String> list_1 = new ArrayList<>(set);
System.out.println("list_1: " + list_1);

//从上可完成Array和Set的互转
//array转set
s = new String[]{"A", "B", "C", "D","E"};
set = new HashSet<>(Arrays.asList(s));
System.out.println("set: " + set);
//set转array
dest = set.toArray(new String[0]);
System.out.println("dest: " + Arrays.toStsecring(dest));
```

### 求最值
```java
import java.util.Arrays;
import java.util.Collections;

public static int MAX(int[] arr) {
    Arrays.sort(arr);
    return arr[arr.length-1];
}

public static void main(String[] args) {
    Integer[] numbers = { 8, 2, 7, 1, 4, 9, 5};
    int min = (int) 
    Collections.min(Arrays.asList(numbers));
    int max = (int) 
    Collections.max(Arrays.asList(numbers));
    System.out.println("最小值: " + min);
    System.out.println("最大值: " + max);

    int a[] = {10, 5, 8};
    int min = Arrays.stream(a).min().getAsInt();
    System.out.println(min);
    min = 
  Collections.min(Arrays.stream(a).boxed().collect(Collectors.toList()));
    System.out.println(min);
    Arrays.sort(a);
    System.out.println(a[0]);
}

public static int MAX(int[] arr) {
    return Arrays.Stream(arr).max().getAsInt();
}

```

## 字符串
```java
String s= "asdefgasdefg";
for(int i=0;i<s.length();i++){
    char c = s.charAt(i);
}
//返回指定字符在字符串中第一次出现处的索引，如果此字符串中没有这样的字符，则返回 -1
s.indexOf('s');
//返回从 fromIndex 位置开始查找指定字符在字符串中第一次出现处的索引，如果此字符串中没有这样的字符，则返回 -1。
s.indexOf('s',2);
s.lastIndexOf('s');
s.lastIndexOf('s',6);
String[] ss = s.split("regex");
//String s = s.substring(int start,int end);
char[] cs = s.toCharArray();
String s1 = s.toLowerCase();//将字符串转换为小写
String s2 = s.toUpperCase();//将字符串转换为大写
String s3 = s.trim();
//String s4 = String.valueOf(object);
String str= "address";
String newstr = str.replace("a", "A");// newstr 的值为 Address

//数组排序
//Arrays.sort();//n*log(n);//重载了四个方法
//        sort(T[] a); 默认是升序排序
//        sort(T[] a,int fromIndex,int toIndex);//按升序排列数组的指定范围。
//        sort(T[] a,Comparator<? super T> c);//根据指定比较器产生的顺序对指定对象数组进行排序。
//        sort(T[] a,int fromIndex,int toIndex,Comparator<? super T> c);//根据指定比较器产生的顺序对指定对象数组的指定对象数组进行排序。
如果降序排列的话，对于Int[] a, 需要先转行成Integer[] b
Arrays.sort(b,Collections.reverseOrder());

```

## 集合
![image](image_2.png)
集合框架
### Collection
- add
- addAll
- clear
- contains
- remove
- size
- toArray
- Collection.sort(Collection c);
- Collection.reverse(Collection c);
### list
- List<Object> list = new ArrayList<>();
- list.add();
- list.get(int index);
- list.remove(int index);
- list.indexOf(Object o);
- list.subList(int start,int end);
- list.toArray(new String[list.size()])；//集合转数组


----
Stack<Object> s = new Stack<>();
pop,peek,push

----

Queue<Object> q = new Queue<>();
q.offer(Object o);
q.peek;
q.poll;

```java
Deque<String> queue = new LinkedList<String>();
queue.offer("c");
System.out.println(queue.peek());
queue.offer("x");

System.out.println(queue.poll());
System.out.println(queue.size());
System.out.println(queue.poll());
System.out.println(queue.isEmpty());

Deque<String> stack = new LinkedList<String>();
stack.push("c");
stack.push("xu");
System.out.println(stack.peek());
stack.pop();
System.out.println(stack.size());
System.out.println(stack.isEmpty());

// 以下情况使用 ArrayList :
// 频繁访问列表中的某一个元素。
// 只需要在列表末尾进行添加和删除元素操作.

// 以下情况使用 LinkedList :
// 你需要通过循环迭代来访问列表中的某些元素。
// 需要频繁的在列表开头、中间、末尾等位置进行添加和删除元素操作。

// 对于双端队列来说，可以使用
LinkedList<T> deque = new LinkedList<>();
LinkedList<String> sites = new LinkedList<String>();
sites.add("Google");
sites.add("Runoob");
sites.add("Taobao");
// 使用 addFirst() 在头部添加元素
sites.addFirst("Wiki");
System.out.println(sites);
//[Wiki, Google, Runoob, Taobao]

LinkedList<String> sites = new LinkedList<String>();
sites.add("Google");
sites.add("Runoob");
sites.add("Taobao");
// 使用 addLast() 在尾部添加元素
sites.addLast("Wiki");
System.out.println(sites);
//[Google, Runoob, Taobao, Wiki]

LinkedList<String> sites = new LinkedList<String>();
sites.add("Google");
sites.add("Runoob");
sites.add("Taobao");
sites.add("Weibo");
// 使用 removeFirst() 移除头部元素
sites.removeFirst();
System.out.println(sites);
//[Runoob, Taobao, Weibo]

LinkedList<String> sites = new LinkedList<String>();
sites.add("Google");
sites.add("Runoob");
sites.add("Taobao");
sites.add("Weibo");
// 使用 removeLast() 移除尾部元素
sites.removeLast();
System.out.println(sites);
//[Google, Runoob, Taobao]

LinkedList<String> sites = new LinkedList<String>();
sites.add("Google");
sites.add("Runoob");
sites.add("Taobao");
sites.add("Weibo");
// 使用 getFirst() 获取头部元素
System.out.println(sites.getFirst());
//Google

LinkedList<String> sites = new LinkedList<String>();
sites.add("Google");
sites.add("Runoob");
sites.add("Taobao");
sites.add("Weibo");
// 使用 getLast() 获取尾部元素
System.out.println(sites.getLast());
// Weibo

// 还可以遍历
LinkedList<String> sites = new LinkedList<String>();
sites.add("Google");
sites.add("Runoob");
sites.add("Taobao");
sites.add("Weibo");
for (int size = sites.size(), i = 0; i < size; i++) {
    System.out.println(sites.get(i));
}
// Google
// Runoob
// Taobao
// Weibo
```

----

Deque<String> dq = new LinkedList<>();
- 当栈用: pop(),push(), peek()
- 当队列用:
offer()
poll()
peek()
- 从头部插入：
addFirst()//将指定的元素插入此双端队列的前面 ，空间不足抛异常
offerFirst()//空间不足插入失败返回回false
push()//空间不足抛异常
- 从尾部插入
add()//将指定的元素插入此双端队列的后面 ，空间不足抛异常
offer()//空间不足返回false
addLast()//同add()
offerLast()//同offer()
- 从头部删除：
E removeFirst()//检索并删除第一个元素，为空时抛出异常
E remove()//同removeFirst
E pop()//同removeFirst
E poll()//检索并删除第一个元素 ，为空时返回null
E pollFirst()//同poll
- 从尾部删除
E removeLast()//检索并删除最后一个元素，为空时抛出异常
E pollLast()//检索并删除最后一个元素 ，为空时返回null
- 检索但不删除
E getFirst()//检索但不删除第一个元素，为空就抛异常
E getLast()//检索不删除最后一个元素，为空就抛异常
E peek() peekFirst()//检索但不删除第一个元素，为空返回null
E peekLast()//检索但不删除最后一个元素，为空返回null

----
迭代器
Iterator<> iterator()

优先队列
Queue<Integer> q = new PriorityQueue<>();默认 小顶堆
peek()//不弹 返回队首元素
poll()//弹出 返回队首元素
add() offer() //添加元素,前者(add)在插入失败时抛出异常，后者(offer)则会返回false。
size()//返回队列元素个数
isEmpty()//判断队列是否为空，为空返回true,不空返回false

PriorityQueue<Integer> queue = new PriorityQueue<Integer>(new Comparator<Integer>() {
@Override
public int compare(Integer num1, Integer num2) {
return num1 - num2;//升序 小顶堆
return num2 - num1;//降序 大顶堆
}
});

get()
put()
remove()

getOrDefault(Object key,V defaultValue);
containsKey()
containValue()
isEmpty()


## 常用算法技巧
### 位运算技巧
https://mp.weixin.qq.com/s?__biz=MzAxODQxMDM0Mw==&mid=2247486704&idx=2&sn=59b011722fe722551de8b56f234a4050&chksm=9bd7f2f8aca07bee47852e7bce72325157897ad0a3d5f383d18bca5379d66716518c2b968ae9&scene=178&cur_album_id=1318896187793260544#rd
1. 利用或操作 `|` 和空格将英文字符转换为小写：
('a' | ' ') = 'a'，
('A' | ' ') = 'a'

2. 利用与操作 `&` 和下划线将英文字符转换为大写：
('b' & '_') = 'B'，
('B' & '_') = 'B'

3. 利用异或操作 `^` 和空格进行英文字符大小写互换：
('d' ^ ' ') = 'D'，
('D' ^ ' ') = 'd'

4. 不用临时变量交换两个数：
int a = 1, b = 2;
a ^= b;
b ^= a;
a ^= b;
// 现在 a = 2, b = 1

5.n&(n-1) 这个操作是算法中常见的，作用是消除数字 n 的二进制表示中的最后一个 1。
![或](./image.png)

```java
//判断一个数是不是2的指数,一个数如果是 2 的指数，那么它的二进制表示一定只含有一个 1：
bool isPowerOfTwo(int n) {
    if (n <= 0) return false;
    return (n & (n - 1)) == 0;
}
```
6.查找只出现一次的元素
异或运算的性质：一个数和它本身做异或运算结果为 0，即 a ^ a = 0；一个数和 0 做异或运算的结果为它本身，即 a ^ 0 = a
例题：
```java
int singleNumber(List<Integer>& nums) {
    int res = 0;
    for (Inter n : nums) {
        res ^= n;
    }
    return res;
}
```

## 比较器
```java
Comparator<Object> cmp = new Comparator<Object>() {
        @Override
        public int compare(Object o1, Object o2) {
            //升序
            return o1-o2;
            //降序
            return o2-o1;
        }
    };

Collections.sort(list, new Comparator<Dog>() {

    @Override
    public int compare(Dog o1, Dog o2) {
            return o2.age - o1.age;
    }
});
        
```

## List
```java
int[] array = new int[] {1, 2, 3};
List<int[]> intArray = Arrays.asList(array);
for (int[] arr:intArray) {
    System.out.println(Arrays.toString(arr));
}
```

## Map
java中如果两个hashMap的key和value都逐一相等，则map1.equals(map2) 为true.

```java
HashMap<Character,Integer> map=new HashMap<>();
        //HashMap tranversal:
        for (Map.Entry<Character, Integer> entry: map.entrySet()) {
            char key = entry.getKey();
            int val = entry.getValue();
            System.out.println(key + " " + val);
        }
        //        Arrays.hashCode(arr);//get the hash of an arr(unique)
        ////use an array to represent hashmap:
        //        int[] tmp = new int[26];
        //        for (char ch: tmp.toCharArray()) {
        //            tmp[ch - 'a']++;
        //        }
```


## Tree

```java
class TreeCompare implements Comparator<String>
        {
            /* Compares keys based on the
               last word's natural ordering */
            public int compare(String a, String b)
            {
                return a.compareToIgnoreCase(b);
            }
        }
        TreeMap<String, Double> tm = new TreeMap<>(new TreeCompare());
        //        tm.containsKey(Object key);
        //        tm.containsValue(Object value);
        //        tm.fistKey();//return the lowest key currently in map
        //        tm.lastKey();//get the last key in sorted map
        //        tm.remove(Object key);
```
TreeMap默认是升序排序的

### 遍历
#### 广度遍历二叉树
```java
class Node {
   public Node left;
   public Node right;
   public int value;

   public Node(Node l, Node r, int v) {
       left = l;
       right = r;
       value = v;
   }
}
public static List<Integer> treeByLevels(Node node)
{
    List<Integer> result = new ArrayList<>();

    Deque<Node> queue = new LinkedList<>();

    if (node == null) return result;
    queue.offer(node);
    while (!queue.isEmpty()) {
        Node tmp = queue.poll();
        result.add(tmp.value);
        if (tmp.left != null) queue.offer(tmp.left);
        if (tmp.right!= null) queue.offer(tmp.right);
    }
    return result;
}

public class BinaryTreeTraversal {
    // 前序遍历
    public void preOrder(TreeNode root) {
        if (root == null) {
            return;
        }
        System.out.print(root.val + " ");
        preOrder(root.left);
        preOrder(root.right);
    }

    // 中序遍历
    public void inOrder(TreeNode root) {
        if (root == null) {
            return;
        }
        inOrder(root.left);
        System.out.print(root.val + " ");
        inOrder(root.right);
    }

    // 后序遍历
    public void postOrder(TreeNode root) {
        if (root == null) {
            return;
        }
        postOrder(root.left);
        postOrder(root.right);
        System.out.print(root.val + " ");
    }

    // 前序遍历
    public void preOrder(TreeNode root) {
        if (root == null) {
            return;
        }

        Stack<TreeNode> stack = new Stack<>();
        stack.push(root);

        while (!stack.isEmpty()) {
            TreeNode node = stack.pop();
            System.out.print(node.val + " ");

            if (node.right != null) {
                stack.push(node.right);
            }
            if (node.left != null) {
                stack.push(node.left);
            }
        }
    }

    // 中序遍历
    public void inOrder(TreeNode root) {
        if (root == null) {
            return;
        }

        Stack<TreeNode> stack = new Stack<>();
        TreeNode current = root;

        while (current != null || !stack.isEmpty()) {
            while (current != null) {
                stack.push(current);
                current = current.left;
            }

            current = stack.pop();
            System.out.print(current.val + " ");
            current = current.right;
        }
    }

    // 后序遍历
    public void postOrder(TreeNode root) {
        if (root == null) {
            return;
        }

        Stack<TreeNode> stack1 = new Stack<>();
        Stack<TreeNode> stack2 = new Stack<>();
        stack1.push(root);

        while (!stack1.isEmpty()) {
            TreeNode node = stack1.pop();
            stack2.push(node);

            if (node.left != null) {
                stack1.push(node.left);
            }
            if (node.right != null) {
                stack1.push(node.right);
            }
        }

        while (!stack2.isEmpty()) {
            System.out.print(stack2.pop().val + " ");
        }
    }

```

字符串相关的题:判断句子是否为全字母句
```java
public boolean checkIfPangram(String sentence) {
        int length = sentence.length();
        if (length < 26) return false;
        int[] mapValue = new int[26];
        char[] charArr = sentence.toCharArray();

        for (char ch: charArr) {
            int index = ch - 'a';
            mapValue[index] = 1;
        }
        for (int num : mapValue) {
            if (num == 0) return false;
        }
        return true;
    }
```
cnblogs.com/joshua-aw/p/6011767.html

1233leetcode
```java
public List<String> removeSubfolders(String[] folder) {

        List<String> result = new ArrayList<>();
        List<String> folderList = Arrays.asList(folder);
        //Arrays.stream(folder).sorted(Comparator.comparingInt(String::length));
        String[] sortFolder = sort(folder);
        System.out.println(Arrays.toString(sortFolder));
        List<Integer> flag = new ArrayList<>();
        int folderLen = sortFolder.length;
        for (int i= 0; i < folderLen; i++){
            if (flag.contains(i)) {
                continue;
            }
            for (int j = i ; j < folderLen;j++) {
                if (sortFolder[i].length() == sortFolder[j].length()) {
                    continue;
                }
                if (flag.contains(j)) {
                    continue;
                }

                if (isParentFile(sortFolder[i],sortFolder[j])) {
                    flag.add(j);
                }
            }
            System.out.println(flag.toString());
        }
        System.out.println(flag.toString());
        for (int i= 0; i < folderLen; i++){
            if (flag.contains(i)) {
                continue;
            }
            result.add(sortFolder[i]);
        }

        return result;
    }

    private static String[] sort(String[] strs) {
        // TODO Auto-generated method stub
        Set<String> set = new TreeSet<>(new Comparator<String>() {

            @Override
            public int compare(String o1, String o2) {
                // TODO Auto-generated method stub
                if (o1.length() < o2.length())
                    return -1;
                else if (o1.length() > o2.length())
                    return 1;
                return o1.compareTo(o2);
            }
        });

        for (String s : strs)
            set.add(s);
        String[] result = new String[strs.length];
        int i = 0;
        for (String s: set) {
            result[i] = s;
            i++;
        }
        return result;
    }
    private boolean isParentFile(String a, String b) {
        int lenthA = a.length();
        if (a.equals(b)) return true;
        if (b.startsWith(a) && b.charAt(lenthA) == '/') {
            return true;
        }

        return false;
    }
```
有些题目可以Map<Key,int[]> map;数据结构
要是对value集合排序是，可以用map.values得到一个Collection<int[]>, 然后对其进行排序。
List.sort()
Collections.sort(List<T>list,Comparator<? super T> c);

```java
opArray.sort(new Comparator<IoRecord>() {
              @Override
              public int compare(IoRecord o1, IoRecord o2) {
                  return (o1.startAddr != o2.startAddr)?(o1.startAddr - o2.startAddr): (o1.endAddr- o2.endAddr);
              }
          });

 opArray.stream()
        .sorted((o1, o2) -> (o1.startAddr != o2.startAddr) ? (o1.startAddr - o2.startAddr) : (o1.endAddr - o2.endAddr))
         collect(Collectors.toList());
// 上面两个排序等价吗？
// 这两种写法实际上是不等价的。
// 第一种写法使用了opArray.sort()方法来对原始数组进行排序，而第二种写法使用了opArray.stream().sorted()方法来创建一个新的排序后的列表。
// opArray.sort()方法会直接修改原始数组的顺序，而opArray.stream().sorted()方法则会返回一个新的排序后的列表，而不会修改原始数组。
// 因此，如果你希望修改原始数组的顺序，应该使用第一种写法；如果你希望得到一个新的排序后的列表，应该使用第二种写法。
```

		
