

![image-20220623215313030](D:\LenovoSoftstore\Typora\photos\image-20220623215313030.png)

[AcWing 831. KMP字符串思路详解(java代码) - AcWing](https://www.acwing.com/solution/content/11332/)

![image-20220623215451796](D:\LenovoSoftstore\Typora\photos\image-20220623215451796.png)

```java
import java.io.BufferedInputStream;
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.OutputStreamWriter;
import java.nio.Buffer;

public class Main {
    public static void main(String[] args) throws NumberFormatException, IOException {
        BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter writer = new BufferedWriter(new OutputStreamWriter(System.out));

        int n = Integer.parseInt(reader.readLine());

        // 模式串
        String pp = reader.readLine();
        char[] p = new char[n + 1];
        for (int i = 1; i <= n; i++) {
            p[i] = pp.charAt(i - 1);
        }

        int m = Integer.parseInt(reader.readLine());
        String ss = reader.readLine();
        // 总串
        char[] s = new char[m + 1];
        for (int i = 1; i <= m; i++) {
            s[i] = ss.charAt(i - 1);
        }
        // 构造前缀数组
        int ne[] = new int[n + 1];

        for (int i = 2, j = 0; i <= n; i++) {
            while (j != 0 && p[i] != p[j + 1])
                j = ne[j];
            if(p[i]==p[j+1]) j++;
            ne[i] = j;
        }

        for (int i = 1, j = 0; i <= m; i++) {
            while (j != 0 && s[i] != p[j + 1])
                j = ne[j];
            if(s[i]==p[j+1]) j++;
            if(j==n){
                writer.write(i-n+" ");
                j = ne[j];
            }
        }
        writer.flush();
        writer.close();
        reader.close();
    }
}
```



```c++
#include<iostream>
using namespace std;
char p[100005];
char s[1000005];
int ne[100005];

int main(){
    int n,m;
    cin>>n>>p+1>>m>>s+1;
    for(int i=2,j=0;i<=n;i++){
        while(j&&p[i]!=p[j+1]) j = ne[j];
        if(p[i]==p[j+1]) j++;
        ne[i] = j;
    }
    
    for(int i=1,j=0;i<=m;i++){
        while(j&&s[i]!=p[j+1]) j = ne[j];
        if(s[i]==p[j+1]) j++;
        if(j==n){
            printf("%d ",i-n);
        }
    }
    return 0;
}
```

