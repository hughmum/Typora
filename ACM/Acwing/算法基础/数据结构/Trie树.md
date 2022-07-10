高效的存储和查找字符串集合的数据结构

```c++
#include<iostream>
#include<String>
using namespace std;
const int N =100010;
int son[N][26],cnt[N],idx = 0;
char str[N];

void insert(char str[]){
    int p = 0;
    for(int i=0;str[i];i++){
        int u  = str[i] - 'a';
        if(!son[p][u]) son[p][u] = ++idx;
        p = son[p][u];
    }
    cnt[p]++;
 
}

void query(char str[]){
    int p = 0;
    for(int i=0;str[i];i++){
        int u = str[i] - 'a';
        if(!son[p][u]){
            cout<<0<<endl;
            return ;
        }
        p = son[p][u];
     }
     cout<<cnt[p]<<endl;
}

int main(){
    int n;
    cin>>n;
    while(n--){
        char op[2];
        scanf("%s%s",op,str);
        if(op[0]=='I')insert(str);
        else{
            query(str);
        }
    }
    return 0;
}
```

```java
import java.util.*;
import java.util.concurrent.ForkJoinPool;

public class Main{
     static int N = 100010;
     static int son[][] = new int[N][26];
     static int cnt[] = new int[N];
     static char str[] = new char[N];
     static int idx = 0;

    public static void insert(char[] str){
        int p = 0;
        for(int i=0;i<str.length;i++){
            int u = str[i]-'a';
            if(son[p][u]==0) son[p][u] = ++idx;
            p = son[p][u];
        }
        cnt[p]++;
    }
    
    public static void query(char str[]){
        int p=0;
        for(int i=0;i<str.length;i++){
            int u = str[i]-'a';
            if(son[p][u]==0){
                System.out.println(0);
                return ;
            }
            p = son[p][u];
        }
        System.out.println(cnt[p]);
    }

    public static void main(String[] args) {
       Scanner sc = new Scanner(System.in);
       int n;
       String op;
       n = sc.nextInt();
       while(n-->0){
        op = sc.next();
        String s = sc.next();
        str = s.toCharArray();
        if("I".equals(op)) insert(str);
        else{
            query(str);
        }
       }
    }

}
```

