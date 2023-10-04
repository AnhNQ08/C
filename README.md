#include<bits/stdc++.h>

using namespace std;

struct NhanVien{
     string ma, ten, sex, bd, add, mst, date;
};

bool cmp(NhanVien a, NhanVien b)
{
     string s = a.bd, t = b.bd;
     int n1 = (s[0]-'0')*10+(s[1]-'0'), t1=(s[3]-'0')*10+s[4]-'0',na1 = stoi(s.substr(6)); 
     int n2 = (t[0]-'0')*10+(t[1]-'0'), t2=(t[3]-'0')*10+t[4]-'0',na2 = stoi(t.substr(6));
     if(na1 != na2) return na1 < na2;
     if(t1 != t2) return t1 < t2;
     return n1 < n2;
}

int cnt = 0;
void nhap(NhanVien &a)
{
     ++cnt;
     if(cnt < 10) a.ma = "0000" + to_string(cnt);
     else a.ma = "000" + to_string(cnt);
     cin.ignore();
     getline(cin,a.ten);
     cin >> a.sex >> a.bd;
     cin.ignore();
     getline(cin,a.add);
     cin >> a.mst >> a.date;
}

void sapxep(NhanVien a[], int n)
{
     sort(a,a+n,cmp);
}

void inds(NhanVien a[], int n)
{
     for(int i = 0; i < n; i++)
     {
          cout << a[i].ma << " " << a[i].ten << " " << a[i].sex << " ";
          cout << a[i].bd << " " << a[i].add << " " << a[i].mst << " ";
          cout << a[i].date << endl;
     }
}

int main(){
    NhanVien ds[50];
    int N,i;
    cin >> N;
    for(i = 0; i < N; i++) nhap(ds[i]);
    sapxep(ds, N);
    inds(ds, N);
    return 0;
}
