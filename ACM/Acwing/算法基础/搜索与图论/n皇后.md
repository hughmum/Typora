## dfs

```c++
#include<iostream>
#include<cstring>
using namespace std;
const int N = 20;
char g[N][N];
bool vis[N],dg[N],udg[N];
int n;
void dfs(int u){
    if(u==n){
        for(int i=0;i<n;i++){
            puts(g[i]);
        }
        puts("");
        return ;
    }
    for(int i=0;i<n;i++){
        if(!vis[i]&&!dg[u+i]&&!udg[n+u-i]){
            g[u][i]='Q';
            vis[i]=dg[u+i]=udg[n+u-i]=true;
            dfs(u+1);
            vis[i]=dg[u+i]=udg[n+u-i]=false;
            g[u][i]='.';
        }
    }
}
int main(){
    cin>>n;
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            g[i][j] = '.';
        }
    }
    dfs(0);
    return 0;
}
```

```java
import java.io.*;

//枚举回溯
public class Main{
    static BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    static char[][] g;
    static int n;
    static boolean[] dg,udg,col,row;
   public static void main(String[] args) throws NumberFormatException, IOException {
     n = Integer.valueOf(br.readLine());
     g = new char[n][n];
     dg = new boolean[n*2];
     udg = new boolean[n*2];
     row = new boolean[n];
     col = new boolean[n];
     for (int i = 0; i < n; i++) {
        for(int j=0;j<n;j++){
            g[i][j] = '.';
        }
     }
     dfs(0,0,0);
   }

   public static void dfs(int x,int y,int s){
    if(y==n) {
        y=0;
        x++;
    }
    if(x==n){
        if(s==n){
            for(int i=0;i<n;i++){
                System.out.println(g[i]);
            }
            System.out.println();
        }
        return ;
    }
    //先不管是否符合条件，先执行不方皇后的情况
    dfs(x,y+1,s);

   
    if(!row[x]&&!col[y]&&!dg[x+y]&&!udg[n+x-y]){
        g[x][y]='Q';
        row[x] = col[y] = dg[x + y] = udg[x - y + n] = true;
        dfs(x,y+1,s+1);
        row[x] = col[y] = dg[x + y] = udg[x - y + n] = false;
        g[x][y]='.';
    }
   }
} 
```

