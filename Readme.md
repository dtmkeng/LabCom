```c
#include <stdio.h>
#include <string.h>
int vowel(char b[]);
int checkChar(char c);
int consonant(char k[]);
int  cnt1=0;cnt2=0;
int main()
{
   int  num,i,count[10],max,j,index=0;
   char s[7][50],ch[50];
   printf("How many string (3-5): ");
   scanf("%d",&num);
   while(num<3||num>5){
		printf("How many string (3-5): ");
		scanf("%d",&num);
   }
	__fpurge(stdin);
  for(i=0;i<num;i++){
		printf("String %d: ",i+1);
	    gets(s[i]);
  }
  for(i=0;i<num;i++){
		count[i]=strlen(s[i]);
	    max=count[0];
	     if(count[i]>max){
			 max=count[i];
			 index++;
		 }    
	  //printf ("%d",count[i]);
  }
	printf ("\n\n");
	printf("Output...\n");
	printf("String %d :\" %s \" is longgest and the length is %d\n",count[index],s[index],strlen(s[index]));
	printf ("\n");
	printf ("In Function vowel()...\n");
	printf ("The vowel is \" ");
	vowel(s[index]);
	printf("\"");
	printf ("\n\n");
	printf ("In Function consonant()...\n");
	printf ("The consonant is \" ");
	consonant(s[index]);
	printf("\"");
	printf ("\n");
	printf("\nIn funtion main()...\n");
	printf("Vowel = %d\n",cnt1);
	printf("Consonant = %d\n",cnt2);
}
int consonant(char k[]){
	int i;
    for(i=0;i<strlen(k);i++){
       if(!(checkChar(k[i]))&&k[i]!=' '){
		 printf("%c",k[i]);
		 cnt2++;
	   }
	}
}
int vowel(char b[]){
	int i;
    for(i=0;i<strlen(b);i++){
       if(checkChar(b[i])&&b[i]!=' '){
		 printf("%c",b[i]);
		  cnt1++;
	   }
	}
}
int checkChar(char c){
	c = toupper(c);
	return (c =='A'||c=='E'||c=='I'||c=='O'||c=='U');
}
```