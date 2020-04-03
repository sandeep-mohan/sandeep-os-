# sandeep-os-
#include<stdio.h>
#include<conio.h>
int main()
{
int bt[10],p[10],n,temp,i,j,wt[10],sum=0;
float avg;
printf("Enter the total number of processes:");
scanf("%d",&n);
printf("\n Enter the burst time for each processes:-");
for(i=0;i<n;i++)
{
printf("\nBurst time of the processes P%d:",i);
scanf("%d",&bt[i]);
p[i]=i;
}
for(i=0;i<n-1;i++)
{
for(j=i+1;j<n;j++)
{
if(bt[i]>bt[j])
{
temp=bt[i];
bt[i]=bt[j];
bt[j]=temp;
temp=p[i];
p[i]=p[j];
p[j]=temp;
}
}
}
wt[0]=0;
for(i=1;i<n;i++)
{
wt[i]=wt[i-1]+bt[i-1];
}
for(i=0;i<n;i++)
{
sum+=wt[i];
}
avg=(float)sum/n;
printf("\n Waiting time for each process is:-");
for(i=0;i<n;i++)
{
printf("\n Waiting time for process P%d is %d
sec.",p[i],wt[i]);
}
printf("\n Average waiting time will be %f sec.",avg);
getch();
return 0;
}
