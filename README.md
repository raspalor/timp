# timp
#include <iostream>
	#include <cstdlib>
	using namespace std;
	int main(int argc, char* argv[]) {
		setlocale(LC_ALL, "Russian");
		if (argc != 4) {
			cout << "Введите пожалуйста в формате (a ; +, -, *, / ; b)" << endl;
	                exit(EXIT_FAILURE);
		}
		double a, b;
		a = atof(argv[1]);
		b = atof(argv[3]);

		try {
			if (b == 0 && argv[2][0] == '/')
				throw 1;

			if (argv[2][0] != '+' && argv[2][0] != '/' && argv[2][0] != '*' && 				argv[2][0] != '-')
				throw 2;

			if ('+' == argv[2][0])
			cout << a + b << endl;
			if ('-' == argv[2][0])
			cout << a - b << endl;
			if ('*' == argv[2][0])
			cout << a * b << endl;
			if ('/' == argv[2][0])
			cout << a / b << endl;
		}
		catch (int i)
		{
			switch (i)
			{
			case 1:
				cout << "Ошибка № 1 - деление на ноль." << endl;
				break;
	
			case 2:
				cout << "Ошибка № 2 - использование некорректного знака." << 			endl;
				break;
			}
		}

		return 0;
	}
