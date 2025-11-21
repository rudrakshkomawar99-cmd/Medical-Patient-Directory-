# Medical-Patient-Directory-
#include <stdio.h>

struct Patient {
    int id;
    char name[50];
    char phone[15];
};

int main() {
    struct Patient p[100];
    int n, i, searchId;
    int found = 0;

    printf("How many patients to enter? ");
    scanf("%d", &n);
    if (n > 100) n = 100;

    for (i = 0; i < n; i++) {
        printf("Patient %d ID: ", i + 1);
        scanf("%d", &p[i].id);

        printf("Patient %d Name: ", i + 1 );
        scanf("%s", p[i].name);

        printf("Patient %d Phone: ", i + 1 );
        scanf("%s", p[i].phone);
    }

    printf("\nEnter patient ID to get information: ");
    scanf("%d", &searchId);

    for (i = 0; i < n; i++) {
        if (p[i].id == searchId) {
            printf("\nPatient info:\n");
            printf("ID   : %d\n", p[i].id);
            printf("Name : %s\n", p[i].name);
            printf("Phone: %s\n", p[i].phone);
            found = 1;
            break;
        }
    }

    if (!found) {
        printf("No patient found with ID %d\n", searchId);
    }

    return 0;
}
