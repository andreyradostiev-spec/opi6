void InputRoute(Trip& t) {
    cin.ignore(10000, '\n');
    cout << "\n===== МАРШРУТ =====\n";

    while (true) {
        cout << "Звідки вас забрати?: ";
        getline(cin, t.from);

        cout << "Куди прямуємо?: ";
        getline(cin, t.to);

        bool fromEmpty = true;
        for (char c : t.from) {
            if (c != ' ' && c != '\t') {
                fromEmpty = false;
                break;
            }
        }

        bool toEmpty = true;
        for (char c : t.to) {
            if (c != ' ' && c != '\t') {
                toEmpty = false;
                break;
            }
        }

        if (fromEmpty || toEmpty) {
            cout << "Помилка! Поля \"Звідки\" та \"Куди\" не можуть бути порожніми.\n";
            continue;
        }

        if (t.from == t.to) {
            cout << "Помилка! Місце відправлення і призначення не можуть збігатися.\n";
            continue;
        }

        break;
    }
}
