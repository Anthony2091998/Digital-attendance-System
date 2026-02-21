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

