# pta-c

#include<stdio.h>
int main (void)
{

	int b, i, j, n, m, count, temp, a[6][6];
	
	scanf("%d%d",&m,&n);
	
	count=b=0;
	
	for(i=0;i<n;i++)
		for(j=0;j<n;j++)
			scanf("%d",&a[i][j]);
			
	for(i=0;i<n;i++){
		count=0;
		while(count<m){
			for(j=n-1;j>0;j--){
				if(j==n-1){
					temp=a[i][0];
					a[i][0]=a[i][j];
					a[i][j]=temp;
				}
				else{
					temp=a[i][j+1];
					a[i][j+1]=a[i][j];
					a[i][j]=temp;
				}
			}
			count++;
		}
	}
	
	for(i=0;i<n;i++){
		if(i>0)
		printf("\n");
		for(j=0;j<n;j++)
			printf("%d ",a[i][j]);
	}
			
}
