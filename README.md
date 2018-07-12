# C
new chicken
#include <conio.h>
#include <stdio.h>
#define max 100
//Nhap ma tran vuong A cap n
void NhapMaTran(int A[max][max], int n)
{
   for(int i = 0; i<n ; i++)
   for(int j = 0; j<n ; j++)
   {
      printf("[%d][%d] =",i,j);
      scanf("%d", &A[i][j]);
   }
}
//Xuat ma tran vuong A cap n
void XuatMaTran(int A[max][max], int n)
{
   for(int i = 0; i<n ; i++)
   {
      printf("\n");
      for(int j = 0; j<n ; j++)
         printf("%d\t",A[i][j]);
   }

}
//Tong hai ma tran A va B luu vao trong ma tran C
void Tong(int A[max][max], int B[max][max], int C[max][max], int n){
   for(int i = 0; i<n ; i++)
   for(int j = 0; j<n ; j++)
      C[i][j] = A[i][j]+B[i][j];
}
//Tich hai ma tran A va B luu vao trong ma tran C
void Tich(int A[max][max], int B[max][max], int C[max][max], int n)
{
   for(int i = 0; i<n ; i++)
   for(int k = 0; k<n ; k++)
   {
      C[i][k] = 0;
      for(int j = 0; j<n ; j++)
         C[i][k] = C[i][k] + A[i][j]*B[j][k];
   }
}
void main()
{
   clrscr();
   int A[max][max],B[max][max], C[max][max], n;
   //nhap cap n
   printf("Nhap cap n= ");
   scanf("%d",&n);
   //nhap ma tran A
   printf("Nhap vao ma tran A\n");
   NhapMaTran(A,n);
   //nhap ma tran B
   printf("Nhap vao ma tran B\n");
   NhapMaTran(B,n);
   //In hai ma tran A va B vua nhap
   printf("Ma tran A vua nhap\n");
   XuatMaTran(A,n);
   printf("\nMa tran B vua nhap\n");
   XuatMaTran(B,n);
   //C=A+B
   Tong(A,B,C,n);
   printf("\nMa tran C=A+B\n");
   XuatMaTran(C,n);
   //C=A*B
   printf("\nMa tran C=A*B\n");
   Tich(A,B,C,n);
   XuatMaTran(C,n);
   getch();
}
