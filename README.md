#include <stdio.h>
#include <stdlib.h>
#include <string.h>


///////////////////////////////////// BY RAYANE BOUCHAIR /////////////////////////////////////////////////////////

                      //les METHODES DE TRIATIONS      / 'TRI A BULLE ' /  'TRI PAR SELECTION ' / 'TRI PAR INSERTION '  /



void triselection (int n,int T[n]){           //TRIE PAR SELECTION MINE ////
int i,x,imin;


i=1;
while (i<n){

 imin=i+1;

 for (int j=imin;j<=n;j++){
   if (T[imin]>T[j]){
    imin=j;
   }
 }
 if (T[imin]<T[i]){
    x=T[i];
    T[i]=T[imin];
    T[imin]=x;
    }
    
  i++;
}
}



void triABulle(int n,int T[n])                         //TRIE A BULLE///
{             

int temp;

 for (int i=n-1;i>=1;i--){          //pour defini l'intervalle de permutation zouj zouj fayan thbeesss
   for (int j=1;j<=i;j++){
       if (T[j]>T[j+1]){
        temp=T[j];
        T[j]=T[j+1];
        T[j+1]=temp;
       }
    }
 }
}




void trieParInsertion(int n,int T[n]){                 //trie par INSERTION //

int itemp,temp,i;

itemp=2;

while (itemp<=n){               //nkhyro l temporelle f la case dernier f tableau 

  i=itemp-1;                    //nbdew ncompariw mn lkhana l9bel temp w habat hta i=0 nhbsoo

  temp=T[itemp];

   while (i>0)
   {
      if (temp<T[i])
      {
         T[i+1]=T[i];
         i--;
      }else break;         //cas kintkon lkhna l9bel temp machi kber mkalah nhbto moraha 
    }
   T[i+1]=temp;

 itemp++; 
  
}
}





void LireTab(int n,int t[n])
{
    for (int i=1;i<=n;++i)
    {
        printf("t[%d] = ",i);
        scanf("%d",&t[i]);
    }
}



void AfficherTab(int n, int t[n])
{
    printf("les elements de tableau:\n");
    for (int i=1;i<=n;++i)
    {
        printf("t[%d] = %d\n",i,t[i]);
    }

}





int main (){
int n=5,choix;

int T[n];
LireTab (n,T);
printf("\n choisir un methode\t 1) par selection \t 2) par trie a bulle \t3) trie par insertion  \n");
scanf("%d",&choix);


switch (choix)
{

case 1:
printf("\n \n par la methode de trie par selection \n\n");
triselection(n,T);
AfficherTab(n,T);

break;
case 2:
printf("\n\n\n La methode de trie a bulle :\n");
triABulle(n,T);
AfficherTab(n, T);
break;


case 3: 
printf("\n\n La methode de trie par insertion \n");
trieParInsertion(n,T);
AfficherTab( n,T);
break;
}



    return 0;
}
