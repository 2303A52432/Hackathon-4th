# Hackathon-4th
https://github.com/user-attachments/assets/f5245dca-c587-459f-b5fc-1a90470bcc42
Team Members:
2303A52432
2303A52284
2303A52460
2303A52379
2303A52181
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct {
    char title[100];
    char topic[50];
    int reading_time; // in minutes
} Resource;

typedef struct {
    char learner_name[50];
    int completed_minutes;
    int total_minutes;
} Progress;

void displayResources(Resource res[], int n) {
    printf("\nAvailable Resources:\n");
    for (int i = 0; i < n; i++) {
        printf("%d. %s [%s] - %d min\n", i+1, res[i].title, res[i].topic, res[i].reading_time);
    }
}

void updateProgress(Progress *p, int minutes) {
    p->completed_minutes += minutes;
    printf("Progress updated! Total completed: %d / %d minutes\n", p->completed_minutes, p->total_minutes);
}

int main() {
    Resource resources[3] = {
        {"Intro to AI", "AI", 45},
        {"Neural Networks", "AI", 60},
        {"Data Structures", "CS", 50}
    };
    Progress learner = {"Alice", 0, 45 + 60 + 50};
    displayResources(resources, 3);
    updateProgress(&learner, 45); // simulate reading one topic
    updateProgress(&learner, 60); // simulate reading another topic
    return 0;
}

