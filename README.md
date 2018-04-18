14.
#include<stdio.h>
#include<conio.h>
void main()
{
             int arr[100],n,initial,i,j,sum=0,diff;
             printf("Enter the size of Queue\n");
             scanf("%d",&n);
             printf("Enter the Queue\n");
             for(i=1;i<=n;i++)
             {
                          A: scanf("%d",&arr[i]);
                          if(arr[i]<0 || arr[i]>4999)
                           {
                             printf("Wrong input, enter again");
                             goto A;

                           }
             }
             printf("Enter the initial position\n");
             scanf("%d",&initial);
             arr[0]=initial;
             printf("\n");
             for(i=0;i<n;i++)
             {
             for(j=i+1;j<n;j++)
             {
                          diff=abs(arr[j]-arr[i]);
                          sum=sum+diff;
                          printf("Move from %d to %d with distance %d\n",arr[i],arr[j],diff);
             }
             }
             printf("\nTotal distance that the disk arm moves is %d\n",sum);
             getch();
}
19.
#include<stdio.h>
void main()
{
int n;
printf("Enter the no. of processes: ");
scanf("%d",&n);
int id[n],bt[n],wt[n],tat[n],p[n],i,j,temp;
for(i=0;i<n;i++)
{
printf("Enter process %d id: ",i+1);
scanf("%d",&id[i]);
printf("Enter process %d burst time: ",i+1);
scanf("%d",&bt[i]);
printf("Enter process %d priority: ",i+1);
scanf("%d",&p[i]);
}
for(i=0;i<4;i++)
{
for(j=i+1;j<11;j++)
{
if(p[i]>p[j])
{
temp=p[i];
p[i]=p[j];
p[j]=temp;
temp=bt[i];
bt[i]=bt[j];
bt[j]=temp;
temp=id[i];
id[i]=id[j];
id[j]=temp;
}
}
wt[i]=0;
}
for(i=0;i<4;i++)
{
for(j=0;j<i;j++)
{
wt[i]=wt[i]+bt[j];
}
tat[i]=wt[i]+bt[i];
}
float avwt=0,avtat=0;
printf("Process\tP\tBT\tWT\tTAT\n");
for(i=0;i<n;i++)
{
printf("%d\t%d\t%d\t%d\t%d\n",id[i],p[i],bt[i],wt[i],tat[i]);
avwt=avwt+wt[i];
avtat=avtat+tat[i];
}
avwt=avwt/n;
avtat=avtat/n;
printf("Average Waiting Time: %f\n",avwt);
printf("\nAverage Turnaround Time: %f",avtat);
}
