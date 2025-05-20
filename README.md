# EX 6 : Two-Dimensional Transformations
## NAME:MAGESHKUMAR U
## REGNO:212224240085

## AIM

To write a c program to implement 2D transformation of image.


## ALGORITHM

Step 1:Start the program.

Step 2:Draw the image with default parameters.

Step 3 : Get the choice from the user.

Step 4: Get the parameters for transformation.

Step 5 : Perform the transformation.

Step 6 : Draw the image.

Step 7 : Stop the program.


## Program :
```
#include<stdio.h> 
#include<math.h> 
#include<conio.h> 
#include<stdlib.h> 
#include<graphics.h> 
int gd=DETECT,gm; 
double x1,x2,y1,y2; 
void draw_cube(double edge[20][3]) 
{ 
int i; 
initgraph(&gd,&gm,"c://turboc3//bgi");
clearviewport(); 
for(i=0;i<19;i++) 
{ 
x1=edge[i][0]+edge[i][2]*(cos(2.3562)); 
y1=edge[i][1]-edge[i][2]*(sin(2.3562)); 
x2=edge[i+1][0]+edge[i+1][2]*(cos(2.3562)); 
y2=edge[i+1][1]-edge[i+1][2]*(sin(2.3562)); 
line(x1+320,240-y1,x2+320,240-y2); 
} 
line(320,240,320,25); 
line(320,240,550,240); 
line(320,240,150,410); 
getch(); 
closegraph(); 
} 
void perspect(double edge[20][3]) 
 
 
 { 
 int ch; 
 int i; 
 float p,q,r; 
 clrscr(); 
 printf("\n -=[ Perspective Projection About ]=-"); 
 printf("\n 1:==>X-Axis "); 
 printf("\n 2:==>Y-Axis "); 
 printf("\n 3:==>Z-Axis "); 
 printf("\n Enter Your Choice :="); 
 scanf("%d",&ch); 
 switch(ch) 
  { 
  case 1: 
   printf("\n Enter P :="); 
   scanf("%f",&p); 
   for(i=0;i<20;i++) 
    { 
    edge[i][0]=edge[i][0]/(p*edge[i][0]+1); 
    edge[i][1]=edge[i][1]/(p*edge[i][0]+1); 
    edge[i][2]=edge[i][2]/(p*edge[i][0]+1); 
    } 
   draw_cube(edge); 
          break; 
  case 2: 
   printf("\n Enter Q :="); 
   scanf("%f",&q); 
   for(i=0;i<20;i++) 
 
 
    { 
    edge[i][1]=edge[i][1]/(edge[i][1]*q+1); 
    edge[i][0]=edge[i][0]/(edge[i][1]*q+1); 
    edge[i][2]=edge[i][2]/(edge[i][1]*q+1); 
    } 
   draw_cube(edge); 
   break; 
  case 3: 
   printf("\n Enter R :="); 
   scanf("%f",&r); 
   for(i=0;i<20;i++) 
    { 
    edge[i][2]=edge[i][2]/(edge[i][2]*r+1); 
    edge[i][0]=edge[i][0]/(edge[i][2]*r+1); 
    edge[i][1]=edge[i][1]/(edge[i][2]*r+1); 
    } 
   draw_cube(edge); 
   break; 
  } 
 closegraph(); 
 } 
 void main() { 
 int choice; 
 double edge[20][3]= { 
   100,0,0,100,100,0,0,100,0,0,100,100,0,0,100,0,0,0, 
   100,0,0,100,0,100,100,75,100,75,100,100,100,100,75, 
   100,100,0,100,100,75,100,75,100,75,100,100,0,100,100, 
   0,100,0,0,0,0,0,0,100,100,0,100 
}; 
clrscr(); 
draw_cube(edge); 
perspect(edge); 
closegraph(); 
}
```

## Output :
![Screenshot (51)](https://github.com/user-attachments/assets/cb3c49a7-cf47-4457-afb5-be5ec5d0b82f)
![Screenshot (52)](https://github.com/user-attachments/assets/f7ff2d1f-aa87-4c34-8d9c-3a6c6b869a74)


## Result :
Successfully implemented a c program to implement 2D transformation of image.
