# pronj
public class JavaSpiralDemo
{
public static void main(String args[])

{

int x = (int)args[0];
int y = (int)args[1];
int length = x*y;
int oplen=0;
String output;

x=x-1;
y=y-1;     

String[][] string2Arr = new String[x][y];


for (int i = 0; i <=x; i++)
   for (int j = 0; j <= y; j++)
	string2Arr[i][j] = args[2 + (i * x + j)];


int s=0;
int t=0;
int z=0;
int xc=0;
int yc=0;

while(oplen<=length){

if(z%2==0)
{
for(;  oplen<=length && t<=y; t++)
{
output = output + "" + string2Arr[s][t];
oplen++;
}
s=s+1;
for(; oplen<=length && s<=x; s++)
{
output = output + "" + string2Arr[s][t];
oplen++;
}
xc+=1;
y=y-1;
t=t-1;
z++;

}

else
{
for(; oplen<=length && t>=yc; t--)
{
output = output + "" + string2Arr[s][t];
oplen++;
}
s=s-1;
for(; oplen<=length && s>=xc; s--)
{
output = output + "" + string2Arr[s][t];
oplen++;
}
yc+=1;
x=x-1;
t=t+1
z++;
}
}

system.out.println(output);

}
}

