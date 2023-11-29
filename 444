#include<bits/stdc++.h>

using namespace std;

inline int read()
{
    char ch=getchar();
    int f=1,x=0;
    while (ch<'0' || ch>'9')
    {
        if (ch=='-') f=-1;
        ch=getchar();
    }
    while (ch>='0' && ch<='9')
    {
        x=x*10+ch-'0';
        ch=getchar();
    }
    return f*x;
}

int n,ans[15],mp[26];
char s[15][15][3];

inline bool check(int x,int y) //检验 (x,y)
{
    int sum=ans[x]+ans[y]; //和
    int cur=s[x][y][1]-'A'; //处理十位
    if (sum>=n-1 && mp[cur]!=1) return 0; //如果和 >=n-1 但没有进位
    if (sum>=n-1) sum-=n-1,cur=s[x][y][2]-'A'; //处理个位
    if (mp[cur]!=sum) return 0; //不相等
    return 1;
}

signed main()
{
    n=read();
    for (int j=1;j<=n;j++) scanf("%s",s[1][j]+1);
    for (int i=2;i<=n;i++)
    {
        int cnt=0;
        for (int j=1;j<=n;j++)
        {
            scanf("%s",s[i][j]+1);
            cnt+=strlen(s[i][j]+1)>=2;
        }
        ans[i]=cnt;
        mp[s[i][1][1]-'A']=cnt;
    }
    for (int i=2;i<=n;i++) for (int j=2;j<=n;j++) if (!check(i,j)) return 0&puts("ERROR!");
    for (int i=2;i<=n;i++) printf("%c=%d ",s[i][1][1],ans[i]);
    return !printf("\n%d",n-1);
}
