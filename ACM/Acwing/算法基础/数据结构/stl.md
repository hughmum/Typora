## vector

```c++
#include<iostream>
#include<vector>
using namespace std;
int main(){
    vector<int> a;
    //遍历vector的三种方式
    for(int i=0;i<10;i++) a.push_back(i);
    for(int i=0;i<a.size();i++)cout<<a[i]<<endl;
    
    for(vector<int>::iterator i = a.begin();i!=a.end();i++)cout<<*i<<endl;
    for(auto i = a.begin();i!=a.end();i++)cout<<*i<<endl;

    //a.begin(),a.end()分别是a[0]和a[a.size()]
    for(auto x:a)cout<<x<<endl;
    
    //黑科技
    vector<int> aa(4,3),bb(3,4);
    if(aa<bb) puts("a<b");
    return 0;
}
```

## pair

```c++
//支持比较运算，以first为第一个关键字（字典序）
    pair<int,string>p;
    pair<int,pair<int,int>>p;
```

## String

```c++
#include<iostream>
#include<vector>
using namespace std;
int main(){
    //string
    string  a ="sdf";
    a+='f';
    //从下标位1开始，长度位2
    cout<<a.substr(1,2)<<endl;
    //输出字符串，要得到其起始地址
    printf("%s\n",a.c_str());
    return 0;
}
```

## queue

```c++
#include<iostream>
#include<queue>
#include<vector>
using namespace std;
int main(){
    //队列push,front,back,pop,size,empty没有clear
    queue<int> q;
    
    q = queue<int> q();
    
    return 0;
}
```

![image-20220711131519286](https://gitee.com/hughmum/typere-drawing-bed/raw/master/img/image-20220711131519286.png)

![image-20220711131543102](https://gitee.com/hughmum/typere-drawing-bed/raw/master/img/image-20220711131543102.png)
