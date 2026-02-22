// attendance_session.h
#ifndef ATTENDANCE_SESSION_H
#define ATTENDANCE_SESSION_H
#include <string>
using namespace std;

class AttendanceSession {
public:
    string courseCode;
    string date;
    string startTime;
    int duration;
    AttendanceSession(string code, string d, string st, int dur);
};
#endif

// attendance_session.cpp
#include "attendance_session.h"
AttendanceSession::AttendanceSession(string code, string d, string st, int dur) {
    courseCode = code;
    date = d;
    startTime = st;
    duration = dur;
}
// attendance_session.cpp (continued)
void createSession() {
    string code, date, startTime;
    int duration;
    cout << "Enter course code: ";
    cin >> code;
    cout << "Enter date: ";
    cin >> date;
    cout << "Enter start time: ";
    cin >> startTime;
    cout << "Enter duration: ";
    cin >> duration;
    AttendanceSession as(code, date, startTime, duration);
    ofstream file("sessions.txt", ios::app);
    file << as.courseCode << "," << as.date << "," << as.startTime << "," << as.duration << endl;
    file.close();
}

// main.cpp (continued)
int main() {
    int choice;
    do {
        cout << "1. Register Student" << endl;
        cout << "2. Create Session" << endl;
        cout << "3. Exit" << endl;
        cin >> choice;
        switch (choice) {
            case 1: registerStudent(); break;
            case 2: createSession(); break;
        }
    } while (choice != 3);
    return 0;
}
// student.cpp (continued)
void viewStudents() {
    ifstream file("students.txt");
    string line;
    while (getline(file, line)) {
        cout << line << endl;
    }
    file.close();
}
