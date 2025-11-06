# cpp-quiz-game
A simple quiz game project made using C++

Code
#include <iostream>
#include <string>
using namespace std;

// Function to display a question
int askQuestion(string question, string a, string b, string c, string d, char correctOption) {
    char answer;
    cout << "\n" << question << endl;
    cout << "a) " << a << endl;
    cout << "b) " << b << endl;
    cout << "c) " << c << endl;
    cout << "d) " << d << endl;
    cout << "Your answer: ";
    cin >> answer;

    if (tolower(answer) == tolower(correctOption)) {
        cout << "✅ Correct!" << endl;
        return 1; // return 1 for correct answer
    } else {
        cout << "❌ Wrong! Correct answer is option " << correctOption << "." << endl;
        return 0;
    }
}

int main() {
    int score = 0;
    string playerName;

    cout << "------------------------------------\n";
    cout << "      🧠 QUIZ GAME IN C++ 🎮        \n";
    cout << "------------------------------------\n";
    cout << "Enter your name: ";
    getline(cin, playerName);

    cout << "\nWelcome, " << playerName << "! Let's start the quiz!\n";
    cout << "Each correct answer = 1 point.\n";

    // Ask questions
    score += askQuestion("1. Who developed the C++ programming language?",
                         "Dennis Ritchie", "James Gosling", "Bjarne Stroustrup", "Guido van Rossum", 'c');

    score += askQuestion("2. Which of the following is not a C++ data type?",
                         "int", "float", "real", "char", 'c');

    score += askQuestion("3. What is the extension of a C++ source file?",
                         ".cp", ".c", ".cpp", ".java", 'c');

    score += askQuestion("4. Which symbol is used to denote a single-line comment in C++?",
                         "//", "/*", "<!--", "#", 'a');

    score += askQuestion("5. Which concept of OOP does C++ support?",
                         "Inheritance", "Encapsulation", "Polymorphism", "All of the above", 'd');

    // Show results
    cout << "\n------------------------------------\n";
    cout << "🎯 Quiz Completed!\n";
    cout << "Player: " << playerName << endl;
    cout << "Your total score: " << score << " out of 5\n";

    if (score == 5)
        cout << "🏆 Excellent! You're a C++ Master!\n";
    else if (score >= 3)
        cout << "👍 Good job! Keep learning.\n";
    else
        cout << "📘 You need more practice. Try again!\n";

    cout << "------------------------------------\n";
    return 0;
}

