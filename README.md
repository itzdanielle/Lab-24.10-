# Lab-24.10-
// This program will read in a group of test scores (positive integers from 1 to 100)
// from the keyboard and then calculate and output the average score
// as well as the highest and lowest score. There will be a maximum of 100 scores.

/* _Arrays as function parameters_
Instructions: Examine the code. Run the program to see how the average is calculated.
Complete this program as directed by adding statements below the 
//Fill in the...   comments.   */

#include <iostream>
using namespace std;

double findAverage(int numbers[], int size);	// finds average of all grades 
int  findHighest(int numbers[], int size);		// finds highest of all grades 
int  findLowest(int numbers[], int size);		// finds lowest of all grades

int main()
{
	int grades[100];	// the array holding the grades, an integer array of 100 elements. 
	int numberOfGrades;	// the number of grades read.
	int pos;			// index to the array.
	float avgOfGrades;	// contains the average of the grades. 
	int highestGrade;	// contains the highest grade.
	int lowestGrade;	// contains the lowest grade.

	// Read in the values into the array 
	pos = 0;
	cout << "Please input a grade from 1 to 100, (or -99 to stop)" << endl;
	cin >> grades[pos];

	while (grades[pos] != -99)
	{
		pos++;
		cout << "Please input a grade from 1 to 100, (or -99 to stop)" << endl;
		cin >> grades[pos];
	}

	numberOfGrades = pos;

	// call to the function to find average
	avgOfGrades = findAverage(grades, numberOfGrades);

	cout << endl << "The average of all the grades is " << avgOfGrades << endl;

	highestGrade = findHighest (grades, numberOfGrades); // Fill in the call to the function that calculates highest grade

	cout << endl << "The highest grade is " << highestGrade << endl;

	lowestGrade = findLowest (grades, numberOfGrades);  // Fill in the call to the function that calculates lowest grade

	cout << endl << "The lowest grade is " << lowestGrade << endl;  // Fill in code to write the lowest to the screen


}

//********************************************************************************
// findAverage
//
// task:	      This function receives an array of integers and its size.
//	              It finds and returns the average of the numbers in the array
// data in:	      array of int numbers
// data returned: average of the numbers in the array
//
//********************************************************************************
double findAverage(int numbers[], int size)
{
	double sum = 0;			// holds the sum of all the numbers

	for (int pos = 0; pos < size; pos++)
		sum = sum + numbers[pos];

	return (sum / size);	// returns the average
}

//****************************************************************************
// findHighest
//
// task:	      This function receives an array of integers and its size.
//	              It finds and returns the highest value of the numbers in 
//                the array
// data in:	      array of int numbers
// data returned: highest value of the numbers in the array
//
//****************************************************************************
int	findHighest(int numbers[], int size)
{
	int highest = numbers[0];  // initialize highest to first element of array
	
	for (int pos = 0; pos < size; pos++)
		if (numbers[pos] > highest)
			highest = numbers[pos];

	return highest;
}

//****************************************************************************
// findLowest
//
// task:	      This function receives an array of integers and its size.
//	              It finds and returns the lowest value of the numbers in 
//                the array
// data in:	      array of integer numbers
// data returned: lowest value of the numbers in the array
//
//****************************************************************************
int	findLowest(int numbers[], int size)
{
	int lowest = numbers[0];  // initialize highest to first element of array
	
	for (int pos = 0; pos < size; pos++)
		if (numbers[pos] < lowest)
			lowest = numbers[pos];

	return lowest;// Fill in the code for this function
}
