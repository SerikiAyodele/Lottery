//Lottery app
//Author's name
//November 20, 2019

#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

void displayArray(int myArray[], int size)
{
	for (int i = 0; i < size; i++)
	{
		cout << myArray[i] << " ";
	}
	cout << endl;
}

int checkMatches(int array1[], int array2[], int size)
{
	int matches = 0;

	for (int i = 0; i < size; i++)
	{
		if (array1[i] == array2[i])
			matches++;
	}

	return matches;
}

int main()
{
	srand(time(0));
	
	int lottery[5];
	int user[5];

	int no_of_matches;

	cout << "Welcome to the lottery program! Let's see if you're our big winner." << endl;
	cout << "You'll enter 5 values in the range 1-5 and see if you match the winning" << endl;
	cout << "number. Let's go!" << endl;

	for (int i = 0; i < 5; i++)
	{
		lottery[i] = (rand()%5) + 1;
	}

	for (int i = 0; i < 5; i++)
	{
		cout << "Number " << (i+1) << ": ";
		cin >> user[i];
	}

	cout << "\nHere's how you did! Drumroll please..." << endl;
	cout << "Your numbers:" << endl;
	displayArray(user, 5);
	cout << "The winning numbers:" << endl;
	displayArray(lottery, 5);

	no_of_matches = checkMatches(user, lottery, 5);

	if (no_of_matches == 5)
	{
		cout << "You are the grand prize winner!" << endl;
	}
	else
	{
		cout << "You matched " << no_of_matches << " numbers." << endl;
	}

	cout << "Thanks for playing!" << endl;

	system("PAUSE");
	return 0;
}