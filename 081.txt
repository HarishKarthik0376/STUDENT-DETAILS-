#include <stdio.h>
#include <string.h>
struct Student{
    char Name[30];
    char RegistrationNo[30];
    char BloodGroup[5];
    char Emergency_PhoneNo[12];
    float CGPA;
};

int main(){
    int n;
    printf("Enter number of students: ");
    scanf("%d",&n);
    struct Student students[n];
    int i;
    for(i=0;i<=n-1;i++){
        printf("Enter name: ");
        scanf("%s",students[i].Name);
        printf("Enter RegNo: ");
        scanf("%s",students[i].RegistrationNo);
        printf("Enter Blood Group: ");
        scanf("%s",students[i].BloodGroup);
        printf("Enter Emergency Contact:  ");
        scanf("%s",&students[i].Emergency_PhoneNo);
        while(strlen(students[i].Emergency_PhoneNo)>10){
            printf("Invalid Info\n");
            printf("Enter Emergency Contact: \n");
            scanf("%f",&students[i].Emergency_PhoneNo);
        }
        printf("Enter overall CGPA: ");
        scanf("%f",&students[i].CGPA);
        while(students[i].CGPA>10.0){
            printf("Invalid Info\n");
            printf("Enter overall CGPA: \n");
            scanf("%f",&students[i].CGPA);
        }
    }
    printf("Data Received Successfully.....\n");
    char search[20];
    printf("Enter Reg No of student you want to find in database: ");
    scanf("%s",search);
    for(i=0;i<=n-1;i++){
        if(strcmp(students[i].RegistrationNo,search)==0){
            printf("Match found! Retrieving Details.....");
            printf("Student's Blood group is: %s\n",students[i].BloodGroup);
            printf("Student's Emergency no is: %ld \n",students[i].Emergency_PhoneNo);
            printf("Student's Reg No is: %s\n",students[i].RegistrationNo);
            printf("Student's CGPA is: %.1f \n",students[i].CGPA);
        }
        else
            printf("%s\n",search);
            printf("%s\n",students[i].Name);
    }
    return 0;
}