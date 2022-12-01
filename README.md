# Hospital_Management_System_Project



#include<stdio.h>

    struct node

    {

    char name[60];

    char address[60];

    char department[50];

    char pblm[100];

    char id[40];

    char room[60];

    char contact[50];

    struct node*next;

    };

    struct node *head;



    void display()

    {



        struct node* temp = head;

        printf("\t\t\t\t\t*-*-*-*-*-*-*-*-*-*-*-* All data *-*-*-*-*-*-*-*-*-*-*-*\n");

        while(temp!=NULL)

        {

            printf("\n");

            printf("\t\t\t\t\t\t\t|-Name: %s\n",temp->name);

            printf("\t\t\t\t\t\t\t|-Id: %s\n",temp->id);

            printf("\t\t\t\t\t\t\t|-Room: %s\n",temp->room);

            printf("\t\t\t\t\t\t\t|-Department: %s\n", temp-> department);

            printf("\t\t\t\t\t\t\t|-Contact: %s\n",temp->contact);

            printf("\t\t\t\t\t\t\t|-Address: %s\n",temp->address);

            temp = temp->next;

            printf("\n");

        }



        return;

    }



    void insert()

    {

        printf("\t\t*-*-*-*-*-*-*-*-*-*-*-*-*-* Insert Patient Data *-*-*-*-*-*-*-*-*-*-*-*-*-*\n");

        struct node *temp =(struct node*)malloc(sizeof(struct node));



         getchar();

        printf("\t\t\t\t\t|-name: ");

        gets(temp->name);





        printf("\t\t\t\t\t  |-Id: ");

        gets(temp->id);





        printf("\t\t\t\t\t      |-Room: ");

        gets(temp->room);





        printf("\t\t\t\t\t        |-contact: ");

        gets(temp->contact);





        printf("\t\t\t\t\t             |-which department: ");

        gets(temp->department);



        printf("\t\t\t\t\t               |-Address: ");

        gets(temp->address);



        temp->next = NULL;



        if(head==NULL){

            head = temp;

            return;

        }

        else{

            temp->next = head;

            head = temp;

            return;

        }

    }



    void insertnur()

    {

        printf("\t\t*-*-*-*-*-*-*-*-*-*-*-*-*-* Insert nurses/ward boys Data *-*-*-*-*-*-*-*-*-*-*-*-*-*\n");

        struct node *temp =(struct node*)malloc(sizeof(struct node));

        printf("\n");

         getchar();

        printf("\t\t\t\t\t  |-name: ");



        gets(temp->name);





        printf("\t\t\t\t\t    |-Id: ");

        gets(temp->id);



        printf("\t\t\t\t\t       |-Room: ");

        gets(temp->room);



        printf("\t\t\t\t\t           |-Problem: ");

        gets(temp->department);





        printf("\t\t\t\t\t             |-contact: ");

        gets(temp->contact);





        printf("\t\t\t\t\t                |-Address: ");

        gets(temp->address);





        temp->next = NULL;



        if(head==NULL){

            head = temp;

            return;

        }

        else{

            temp->next = head;

            head = temp;

            return;

        }

    }

        void insertdoctor()



    {

        printf("\t\t*-*-*-*-*-*-*-*-*-*-*-*-*-* Insert doctor Data *-*-*-*-*-*-*-*-*-*-*-*-*-*\n");

        struct node *temp =(struct node*)malloc(sizeof(struct node));

        printf("\n");

         getchar();

        printf("\t\t\t\t\t  |-Name: ");

        gets(temp->name);





        printf("\t\t\t\t\t     |-Id: ");

        gets(temp->id);



        printf("\t\t\t\t\t        |-Chamber No: ");

        gets(temp->room);



        printf("\t\t\t\t\t          |-Contact: ");

        gets(temp->contact);



        printf("\t\t\t\t\t             |-Department: ");

        gets(temp->department);



        printf("\t\t\t\t\t                |-Address: ");

        gets(temp->address);



        temp->next = NULL;



        if(head==NULL){

            head = temp;

            return;

        }

        else{

            temp->next = head;

            head = temp;

            return;

        }

    }



    void deletData()

    {

        printf("\t\t*-*-*-*-*-*-*-*-*-*-*-*-*-* Delete Data *-*-*-*-*-*-*-*-*-*-*-*-*-*\n");

        char id[30];

        printf("\t\t\t\t\t  |-Enter ID: ");

        getchar();

        gets(id);

        struct node *temp = head;

        struct node *pretemp = temp;

        if(strcmp(temp->id, id)== 0)

        {

            head = temp-> next;

            free(temp);

            return;

        }

        while(temp != NULL)

        {



            if(strcmp(temp->id, id)== 0)

                break;



           pretemp = temp;

            temp = temp->next;

        }

        pretemp->next = temp->next;

        free(temp);

        return;

    }



    void updateData()

    {

        printf("\t\t*-*-*-*-*-*-*-*-*-*-*-*-*-* Update Data *-*-*-*-*-*-*-*-*-*-*-*-*-*\n");

        char id[30];

        printf("\t\t\t\t\t  |-Enter ID: ");

        getchar();

        gets(id);

        struct node *temp = head;



        while(temp != NULL)

        {



            if(strcmp(temp->id, id)== 0)

                break;

            temp = temp->next;

        }

        printf("\t\t*-*-*-*-*-*-*-*-*-*-*-*-*-* Old Data *-*-*-*-*-*-*-*-*-*-*\n");

        printf("\t\t\t\t\t  |-Old Name: %s\n",temp->name);

        printf("\t\t\t\t\t  |-Old Contact: %s\n",temp->contact);

        printf("\t\t\t\t\t  |-New Data: \n");

        printf("\t\t\t\t\t    |-Name : ");

        gets(temp->name);

        printf("\t\t\t\t\t      |-contact : ");

        gets(temp->contact);

        return;

    }



void totalbill()

{

    int patientid,sit,day,operationcharge,doctorvisit;

    float totalbil;



    printf("\t\t\t\t\t  |-Enter Patient Id: ");

    scanf("%d",&patientid);

    printf("\t\t\t\t\t    |-Enter bed fee: ");

    scanf("%d",&sit);

    printf("\t\t\t\t\t      |-Enter day: ");

    scanf("%d",&day);

    printf("\t\t\t\t\t        |-Enter operation and others charge: ");

    scanf("%d",&operationcharge);

    printf("\t\t\t\t\t           |-Enter doctor visit: ");





    scanf("%d",&doctorvisit);

    totalbil=(sit*day+operationcharge+doctorvisit);

    printf("\n");

    printf("\t\t\t\t\t             |-total pay = %0.2f\n",totalbil);

    printf("\n");

    return 0;

}



int main()



{

   printf("                                  *********************************************** \n");

    printf("                                 *                                                 *\n");

    printf("                                 *              HOSPITAL MANAGEMENT SYSTEM         *\n");

    printf("                                 *                                                 *\n");

    printf("                                  *********************************************** \n");

    printf("........................................................................................................................");





    printf("\t\t\t                          ---------------                    \n");

    printf("\t\t\t                         | Group Members |                   \n");

    printf("\t\t\t                          ---------------                    \n");



    printf("\t\t\t     ,------------------------------------------------------,\n");

    printf("\t\t\t     |             |1| Bijoy Dhar [202-15-3830]             |\n");

    printf("\t\t\t     `------------------------------------------------------`\n");

    printf("\t\t\t     ,------------------------------------------------------,\n");

    printf("\t\t\t     |          |2| Nahid Arman Fahim [202-15-3831]         |\n");

    printf("\t\t\t     `------------------------------------------------------`\n");

    printf("\t\t\t     ,------------------------------------------------------,\n");

    printf("\t\t\t     |         |3| Monir Husain Shuvo [202-15-3853]         |\n");

    printf("\t\t\t     `------------------------------------------------------`\n");

    printf("\t\t\t     ,------------------------------------------------------,\n");

    printf("\t\t\t     |        |4| MD.Aminul Islam Rakib [202-15-3832]       |\n");

    printf("\t\t\t     `------------------------------------------------------`\n");

    printf("\t\t\t     ,------------------------------------------------------,\n");

    printf("\t\t\t     |         |5| S.M. Fardin Foyes Riad[02-15-3846]       |\n");

    printf("\t\t\t     `------------------------------------------------------`\n");

    printf("\n");

    printf("\n");



    printf("                                                     ~~ \n");

    printf("                                               ~~         ~~\n");

    printf("                                            ~~~               ~~~\n");

    printf("                                        ~~~~~~     WELCOME     ~~~~~~\n");

    printf("                                            ~~~               ~~~\n");

    printf("                                                ~~        ~~\n");

    printf("                                                     ~~ \n");

    printf("\n");

    printf("\n");

    int n;

    while(1){

        printf("                          *.*.*.*.*.****************************************.*.*.*.*\n");

        printf("                             ************************ .Main Menu. **************\n");

        printf("                             **************************************************\n");

        printf("                             ************** 1. Add Patient Data      **********\n");

        printf("                             ************** 2. Add Doctor Data       **********\n");

        printf("                             ************** 3. Add nurses/ward boys  **********\n");

        printf("                             ************** 4. Remove data           **********\n");

        printf("                             ************** 5. Update Data           **********\n");

        printf("                             ************** 6. Show all data         **********\n");

        printf("                             ************** 7. Total Bill            **********\n");

        printf("                             ************** 8. Exit                  **********\n");

        printf("                             **************************************************\n");

        printf("\n");

        printf("\t\t\tYour Choice: ");

        scanf("%d",&n);

        printf("\n");

        switch(n)

        {

        case 1:

            insert();

            break;

        case 2:

            insertdoctor();

            break;

        case 3:

            insertnur();

            break;

        case 4:

            deletData();

            break;

        case 5:

            updateData();

            break;

        case 6:

            display();

            break;

        case 7:

            totalbill();

            break;

        case 8:



            return 0;

            break;



        default:

            printf("invalid input\n");

            break;

        }

    }

    return 0;

}

