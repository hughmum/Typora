[786. 第k个数 - AcWing题库](https://www.acwing.com/problem/content/788/)

在原本的快排中加入条件判断，如果k小于s1就递归排序左半边，反之则是右边，时间复杂度为

![image-20220626001939390](https://gitee.com/hughmum/typere-drawing-bed/raw/master/img/image-20220626001939390.png)

时间复杂度就是2n

左边界就是j-l+1

```c++
#include<iostream>
using namespace std;
int q[100005];
int quick_sort(int l,int r,int k){
    if(l==r) return q[l];
    int i = l-1,j = r+1;
    int x = q[l+r>>1];
    while(i<j){
        while(q[++i]<x);
        while(q[--j]>x);
        if(i<j) swap(q[i],q[j]);
    }
    if(k<=j) return quick_sort(l,j,k);
    else{
       return  quick_sort(j+1,r,k);
    }
}
int main(){
    int n,k;
    cin>>n>>k;
    for(int i=0;i<n;i++){
        scanf("%d",&q[i]);
    }
    cout<<quick_sort(0,n-1,k-1);
    return 0;
}
```

