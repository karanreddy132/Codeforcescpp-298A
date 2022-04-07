# Codeforcescpp-298A
#include <bits/stdc++.h>
using namespace std;

int main() {
	int n,s(0),t(0),L(0),R(0),flag(0);
  string str;
  cin >> n;
  cin >> str;
  for(int i=0;i<n;i++){
    if(str[i]=='L')
      L++;
    else if(str[i]=='R')
      R++;
  }
  int i=0;
  while(i<n && flag==0){
    if(str[i]=='L'){
      if(R==0){
        t = i;
        s = i+L;
      }
    }
    else if(str[i]=='R'){
      if(L==0){
        s = i+1;
        t = s+R;
      }
      else{
        s = i+1;
        t = s+R-1;
      }
    }
    if(s && t){
      flag = 1;
      cout << s << " " << t;
    }
    i++;
  }
	return 0;
}
