Download Link: https://assignmentchef.com/product/solved-fraction-assignment
<br>
5/5 - (3 votes)

This week you’ll be making the following refinements to the class that you wrote last week. Your score on this assignment will take into consideration your work on both the previous assignment and this assignment.



Reduce Fractions [5 points]

Add a private “simplify()” function to your class and call it from the appropriate member functions. (If you write your code the way that 90% of students write it, there will be 6 places where you need to call it. But if you call it a different number of times and your class works, that’s also fine.) The best way to do this is to make the function a void function with no parameters that reduces the calling object.

Recall that “simplifying” or “reducing” a Fraction is a separate task from converting it from an improper Fraction to a mixed number. Make sure you keep those two tasks separate in your mind.

For now (until you get down to the part of the assignment where you improve your insertion operator) your Fractions will still be printed as improper Fractions, not mixed numbers. In other words, 19/3 will still be 19/3, not 6+1/3. Make sure that your class will reduce ANY Fraction, not just the Fractions that are tested in the provided client program. Fractions should not be simply reduced upon output, they should be stored in reduced form at all times. In other words, you should ensure that all Fraction objects are reduced before the end of any member function. To put it yet another way: each member function must be able to assume that all Fraction objects are in simple form when it begins execution.

You must create your own algorithm for reducing Fractions. Don’t look up an already existing algorithm for reducing Fractions or finding GCF. The point here is to have you practice solving the problem on your own. In particular, don’t use Euclid’s algorithm. Don’t worry about being efficient. It’s fine to have your function check every possible factor, even if it would be more efficient to just check prime numbers. Just create something of your own that works correctly on ANY Fraction.

Your simplify() function should also ensure that the denominator is never negative. If the denominator is negative, fix this by multiplying numerator and denominator by -1. Also, if the numerator is 0, the denominator should be set to 1.

Better Insertion Operator

Now modify your overloaded &lt;&lt; operator so that improper Fractions are printed as mixed numbers. Whole numbers should print without a denominator (e.g. not 3/1 but just 3). Improper Fractions should be printed as a mixed number with a + sign between the two parts (2+1/2). Negative Fractions should be printed with a leading minus sign.

Note that your class should have only two data members. Fractions will be stored as improper Fractions. The &lt;&lt; operator is responsible for printing the improper Fraction as a mixed number. Also, the ‘+’ in mixed numbers does not mean add. It is simply a separator (to separate the integer part from the Fraction part of the number). So the Fraction “negative two and one-sixth” would be written as -2+1/6, even though -2 plus 1/6 is not what we mean.

Extraction Operator

You should be able to read any of the formats described above (mixed number, negative number, whole numbers, etc.). You may assume that there are no spaces or formatting errors in the Fractions that you read. This means, for example, that in a mixed number only the whole number (not the numerator or denominator) may be negative, and that in a fraction with no whole number part only the numerator (not the denominator) may be negative. Note: You may need to exceed 15 lines for this function. My solution is about 20 lines long.

Since your extraction operator should not consume anything after the end of the Fraction being read, you will probably want to use the .peek() function to look ahead in the input stream and see what the next character is after the first number is read. If it’s not either a ‘/” or a ‘+’, then you are done reading and should read no further. I have something like this:

int temp;

in temp;

if (in.peek() == ‘+’){

doSomething…

} else if (in.peek() == ‘/’){

doSomethingElse…

} else {

doThirdOption

}

Hint: You don’t need to detect or read the minus operator as a separate character. When you use the extraction operator to read an int, it will interpret a leading minus sign correctly. So, for example, you shouldn’t have “if (in.peek() == ‘-‘)”

Hint: The peek() function does not consume the character from the input stream, so after you use it to detect what the next character is, the first thing you need to do is get past that character. One good way to do that would be to use in.ignore(), which ignores one single character in the input stream.

Three Files and Namespaces

Split the project up into three files: client file, implementation file, and header (specification) file. Also, place the class declaration and implementation in a namespace. Normally one would call a namespace something more likely to be unique, but for purposes of convenience we will all call our namespace “cs_Fraction”. Namespaces are covered in lesson 16.15.

Add Documentation

See Style Convention 1, especially Style Convention 1D.

Every public member function and friend function, however simple, must have a precondition (if there is one) and a postcondition listed in the header file. Here is a two part explanation of pre- and post- conditions. You’ll have to download these to view them: part 1, part 2.

The most complex of your function definitions will need additional comment in the implementation file. Most of the function definitions in the implementation file will not need a comment.

Hints about reading input files:

I suggest that you copy the text from the input file webpage(s) and paste it into a file that you have created using your IDE. The files you create when you type in your IDE are always text files (even if they don’t end with .txt). If you’re using Windows, you could also use Notepad, but there’s no reason to open another application when you are already working in your IDE. I strongly suggest that you don’t use TextEdit (Mac) or Word, because these do not store files as text files by default.

Where to save your input file so that your IDE can find it:

In Visual C++, right click on the name of the project in the solution explorer. It appears in bold there. Unless you chose a different name for the project, it will be ConsoleApplication1. From the drop-down menu, choose “show folder in windows explorer”. The folder that opens up will be the correct place to save your file.

In Xcode, while on the project navigator tab (looks like a folder) you’ll see a yellow folder called Products. click the expansion triangle next to it and your project executable should show up. right click it and choose show in finder. The folder it’s in pops up and you can add your input file to that folder.

Here is a tutorial video created by a former student about creating and placing input files in the right spot for Xcode to find them. It’s an alternate method. I would suggest watching this video only if the suggestion above doesn’t seem to be working for you. In order for these instructions to work, you must have executed a program in your project at least once. Otherwise the folder named “debug” that the video refers to will not exist.

Extensions are part of the file name. If you want to count the words in a file named “myfile.txt”, typing “myfile” or “myfile.cpp” won’t work.

For Windows users, before you start this assignment, I suggest that you make sure that Windows is showing you the complete file name of your files, including the extensions. Windows hides this from you by default. In Windows 7 and 8 the procedure is as follows:

1.    Choose “control panel” from the start menu

2.    Choose “Folder Options” from the list of control panel items. In Windows 8 you may have to type “Folder Options” into the control panel search bar.

3.    Choose the “view” tab from the Folder Options window

4.    Find the checkbox that says “Hide extensions for known file types”.

5.    Uncheck that checkbox.

I’ve received two different suggestions from student about how to do this in Windows 10. One student says that the procedure is exactly the same as that outlined above, except that the “Folder Options” window is now the “File Explorer Options” window. The other student says this: go to file explorer and click “View” on the toolbar, then go to “Options” on the furthest right, click on the drop down arrow and choose “Change folder and search options”. Click “View” on the top and uncheck “Hide extensions for known file types”.

Please let me know if you find that this doesn’t work. Also let me know if you think that one of the two Windows 10 options is clearly better.

Client program

#include &lt;iostream

#include “Fraction.h”

#include &lt;fstream

#include &lt;cassert

#include &lt;string

using namespace std;

using namespace cs_Fraction;

void BasicTest();

void RelationTest();

void BinaryMathTest();

void MathAssignTest();

bool eof(ifstream&amp; in);

string boolString(bool convertMe);

int main()

{

BasicTest();

RelationTest();

BinaryMathTest();

MathAssignTest();

}

void BasicTest()

{

cout &lt;&lt; “
—– Testing basic Fraction creation &amp; printing
”;

cout &lt;&lt; “(Fractions should be in reduced form, and as mixed numbers.)
”;

const Fraction fr[] = {Fraction(4, 8), Fraction(-15,21),

Fraction(10), Fraction(12, -3),

Fraction(), Fraction(28, 6), Fraction(0, 12)};

for (int i = 0; i &lt; 7; i++){

cout &lt;&lt; “Fraction [” &lt;&lt; i &lt;&lt;“] = ” &lt;&lt; fr[i] &lt;&lt; endl;

}

cout &lt;&lt; “
—– Now reading Fractions from file
”;

ifstream in(“Fraction.txt”);

assert(in);

while (!eof(in)) {

Fraction f;

if (in.peek() == ‘#’) {

in.ignore(128, ‘
’);                       //skip this line, it’s a comment

} else {

in f;

cout &lt;&lt; “Read Fraction = ” &lt;&lt; f &lt;&lt; endl;

}

}

}

bool eof(ifstream&amp; in)

{

char ch;

in ch;

in.putback(ch);

return !in;

}

string boolString(bool convertMe) {

if (convertMe) {

return “true”;

} else {

return “false”;

}

}

void RelationTest()

{

cout &lt;&lt; “
—– Testing relational operators between Fractions
”;

const Fraction fr[] =  {Fraction(3, 6), Fraction(1,2), Fraction(-15,30),

Fraction(1,10), Fraction(0,1), Fraction(0,2)};

for (int i = 0; i &lt; 5; i++) {

cout &lt;&lt; “Comparing ” &lt;&lt; fr[i] &lt;&lt; ” to ” &lt;&lt; fr[i+1] &lt;&lt; endl;

cout &lt;&lt; “tIs left &lt; right? ” &lt;&lt; boolString(fr[i] &lt; fr[i+1]) &lt;&lt; endl;

cout &lt;&lt; “tIs left &lt;= right? ” &lt;&lt; boolString(fr[i] &lt;= fr[i+1]) &lt;&lt; endl;

cout &lt;&lt; “tIs left right? ” &lt;&lt; boolString(fr[i] fr[i+1]) &lt;&lt; endl;

cout &lt;&lt; “tIs left = right? ” &lt;&lt; boolString(fr[i] = fr[i+1]) &lt;&lt; endl;

cout &lt;&lt; “tDoes left == right? ” &lt;&lt; boolString(fr[i] == fr[i+1]) &lt;&lt; endl;

cout &lt;&lt; “tDoes left != right ? ” &lt;&lt; boolString(fr[i] != fr[i+1]) &lt;&lt; endl;

}

cout &lt;&lt; “
—– Testing relations between Fractions and integers
”;

Fraction f(-3,6);

int num = 2;

cout &lt;&lt; “Comparing ” &lt;&lt; f &lt;&lt; ” to ” &lt;&lt; num &lt;&lt; endl;

cout &lt;&lt; “tIs left &lt; right? ” &lt;&lt; boolString(f &lt; num) &lt;&lt; endl;

cout &lt;&lt; “tIs left &lt;= right? ” &lt;&lt; boolString(f &lt;= num) &lt;&lt; endl;

cout &lt;&lt; “tIs left right? ” &lt;&lt; boolString(f num) &lt;&lt; endl;

cout &lt;&lt; “tIs left = right? ” &lt;&lt; boolString(f = num) &lt;&lt; endl;

cout &lt;&lt; “tDoes left == right? ” &lt;&lt; boolString(f == num) &lt;&lt; endl;

cout &lt;&lt; “tDoes left != right ? ” &lt;&lt; boolString(f != num) &lt;&lt; endl;

Fraction g(1,4);

num = -3;

cout &lt;&lt; “Comparing ” &lt;&lt; num &lt;&lt; ” to ” &lt;&lt; g &lt;&lt; endl;

cout &lt;&lt; “tIs left &lt; right? ” &lt;&lt; boolString(num &lt; g) &lt;&lt; endl;

cout &lt;&lt; “tIs left &lt;= right? ” &lt;&lt; boolString(num &lt;= g) &lt;&lt; endl;

cout &lt;&lt; “tIs left right? ” &lt;&lt; boolString(num g) &lt;&lt; endl;

cout &lt;&lt; “tIs left = right? ” &lt;&lt; boolString(num = g) &lt;&lt; endl;

cout &lt;&lt; “tDoes left == right? ” &lt;&lt; boolString(num == g) &lt;&lt; endl;

cout &lt;&lt; “tDoes left != right ? ” &lt;&lt; boolString(num != g) &lt;&lt; endl;

}

void BinaryMathTest()

{

cout &lt;&lt; “
—– Testing binary arithmetic between Fractions
”;

const Fraction fr[] = {Fraction(1, 6), Fraction(1,3),

Fraction(-2,3), Fraction(5), Fraction(-4,3)};

for (int i = 0; i &lt; 4; i++) {

cout &lt;&lt; fr[i] &lt;&lt; ” + ” &lt;&lt; fr[i+1] &lt;&lt; ” = ” &lt;&lt; fr[i] + fr[i+1] &lt;&lt; endl;

cout &lt;&lt; fr[i] &lt;&lt; ” – ” &lt;&lt; fr[i+1] &lt;&lt; ” = ” &lt;&lt; fr[i] – fr[i+1] &lt;&lt; endl;

cout &lt;&lt; fr[i] &lt;&lt; ” * ” &lt;&lt; fr[i+1] &lt;&lt; ” = ” &lt;&lt; fr[i] * fr[i+1] &lt;&lt; endl;

cout &lt;&lt; fr[i] &lt;&lt; ” / ” &lt;&lt; fr[i+1] &lt;&lt; ” = ” &lt;&lt; fr[i] / fr[i+1] &lt;&lt; endl;

}

cout &lt;&lt; “
—– Testing arithmetic between Fractions and integers
”;

Fraction f(-1, 2);

int num = 4;

cout &lt;&lt; f &lt;&lt; ” + ” &lt;&lt; num &lt;&lt; ” = ” &lt;&lt; f + num &lt;&lt; endl;

cout &lt;&lt; f &lt;&lt; ” – ” &lt;&lt; num &lt;&lt; ” = ” &lt;&lt; f – num &lt;&lt; endl;

cout &lt;&lt; f &lt;&lt; ” * ” &lt;&lt; num &lt;&lt; ” = ” &lt;&lt; f * num &lt;&lt; endl;

cout &lt;&lt; f &lt;&lt; ” / ” &lt;&lt; num &lt;&lt; ” = ” &lt;&lt; f / num &lt;&lt; endl;

Fraction g(-1, 2);

num = 3;

cout &lt;&lt; num &lt;&lt; ” + ” &lt;&lt; g &lt;&lt; ” = ” &lt;&lt; num + g &lt;&lt; endl;

cout &lt;&lt; num &lt;&lt; ” – ” &lt;&lt; g &lt;&lt; ” = ” &lt;&lt; num – g &lt;&lt; endl;

cout &lt;&lt; num &lt;&lt; ” * ” &lt;&lt; g &lt;&lt; ” = ” &lt;&lt; num * g &lt;&lt; endl;

cout &lt;&lt; num &lt;&lt; ” / ” &lt;&lt; g &lt;&lt; ” = ” &lt;&lt; num / g &lt;&lt; endl;

}

void MathAssignTest()

{

cout &lt;&lt; “
—– Testing shorthand arithmetic assignment on Fractions
”;

Fraction fr[] = {Fraction(1, 6), Fraction(4),

Fraction(-1,2), Fraction(5)};

for (int i = 0; i &lt; 3; i++) {

cout &lt;&lt; fr[i] &lt;&lt; ” += ” &lt;&lt; fr[i+1] &lt;&lt; ” = “;

cout &lt;&lt; (fr[i] += fr[i+1]) &lt;&lt; endl;

cout &lt;&lt; fr[i] &lt;&lt; ” -= ” &lt;&lt; fr[i+1] &lt;&lt; ” = “;

cout &lt;&lt; (fr[i] -= fr[i+1]) &lt;&lt; endl;

cout &lt;&lt; fr[i] &lt;&lt; ” *= ” &lt;&lt; fr[i+1] &lt;&lt; ” = “;

cout &lt;&lt; (fr[i] *= fr[i+1]) &lt;&lt; endl;

cout &lt;&lt; fr[i] &lt;&lt; ” /= ” &lt;&lt; fr[i+1] &lt;&lt; ” = “;

cout &lt;&lt; (fr[i] /= fr[i+1]) &lt;&lt; endl;

}

cout &lt;&lt; “
—– Testing shorthand arithmetic assignment using integers
”;

Fraction f(-1, 3);

int num = 3;

cout &lt;&lt; f &lt;&lt; ” += ” &lt;&lt; num &lt;&lt; ” = “;

cout &lt;&lt; (f += num) &lt;&lt; endl;

cout &lt;&lt; f &lt;&lt; ” -= ” &lt;&lt; num &lt;&lt; ” = “;

cout &lt;&lt; (f -= num) &lt;&lt; endl;

cout &lt;&lt; f &lt;&lt; ” *= ” &lt;&lt; num &lt;&lt; ” = “;

cout &lt;&lt; (f *= num) &lt;&lt; endl;

cout &lt;&lt; f &lt;&lt; ” /= ” &lt;&lt; num &lt;&lt; ” = “;

cout &lt;&lt; (f /= num) &lt;&lt; endl;

cout &lt;&lt; “
—– Testing increment/decrement prefix and postfix
”;

Fraction g(-1, 3);

cout &lt;&lt; “Now g = ” &lt;&lt; g &lt;&lt; endl;

cout &lt;&lt; “g++ = ” &lt;&lt; g++ &lt;&lt; endl;

cout &lt;&lt; “Now g = ” &lt;&lt; g &lt;&lt; endl;

cout &lt;&lt; “++g = ” &lt;&lt; ++g &lt;&lt; endl;

cout &lt;&lt; “Now g = ” &lt;&lt; g &lt;&lt; endl;

cout &lt;&lt; “g– = ” &lt;&lt; g– &lt;&lt; endl;

cout &lt;&lt; “Now g = ” &lt;&lt; g &lt;&lt; endl;

cout &lt;&lt; “–g = ” &lt;&lt; –g &lt;&lt; endl;

cout &lt;&lt; “Now g = ” &lt;&lt; g &lt;&lt; endl;

}

Data file

# This file shows the patterns your Fraction class needs to be able to

# read.  A Fraction may be just a single integer, two integers separated by

# a slash, or a mixed number which consists of an integer, followed by a


# and then two integers with a slash.  A minus sign may appear in the

# very first character to indicate the whole Fraction is negative.

# No white space is allowed in between the component parts of a Fraction.

#

1/3

3/6

3072/4096

-4/5

12/2

5

-8

21/15

-50/3

1+1/4

1+5/5

-4+3/12

-10+10/12

Correct output

—– Testing basic Fraction creation &amp; printing

(Fractions should be in reduced form, and as mixed numbers.)

Fraction [0] = 1/2

Fraction [1] = -5/7

Fraction [2] = 10

Fraction [3] = -4

Fraction [4] = 0

Fraction [5] = 4+2/3

Fraction [6] = 0

—– Now reading Fractions from file

Read Fraction = 1/3

Read Fraction = 1/2

Read Fraction = 3/4

Read Fraction = -4/5

Read Fraction = 6

Read Fraction = 5

Read Fraction = -8

Read Fraction = 1+2/5

Read Fraction = -16+2/3

Read Fraction = 1+1/4

Read Fraction = 2

Read Fraction = -4+1/4

Read Fraction = -10+5/6

—– Testing relational operators between Fractions

Comparing 1/2 to 1/2

Is left &lt; right? false

Is left &lt;= right? true

Is left right? false

Is left = right? true

Does left == right? true

Does left != right ? false

Comparing 1/2 to -1/2

Is left &lt; right? false

Is left &lt;= right? false

Is left right? true

Is left = right? true

Does left == right? false

Does left != right ? true

Comparing -1/2 to 1/10

Is left &lt; right? true

Is left &lt;= right? true

Is left right? false

Is left = right? false

Does left == right? false

Does left != right ? true

Comparing 1/10 to 0

Is left &lt; right? false

Is left &lt;= right? false

Is left right? true

Is left = right? true

Does left == right? false

Does left != right ? true

Comparing 0 to 0

Is left &lt; right? false

Is left &lt;= right? true

Is left right? false

Is left = right? true

Does left == right? true

Does left != right ? false

—– Testing relations between Fractions and integers

Comparing -1/2 to 2

Is left &lt; right? true

Is left &lt;= right? true

Is left right? false

Is left = right? false

Does left == right? false

Does left != right ? true

Comparing -3 to 1/4

Is left &lt; right? true

Is left &lt;= right? true

Is left right? false

Is left = right? false

Does left == right? false

Does left != right ? true

—– Testing binary arithmetic between Fractions

1/6 + 1/3 = 1/2

1/6 – 1/3 = -1/6

1/6 * 1/3 = 1/18

1/6 / 1/3 = 1/2

1/3 + -2/3 = -1/3

1/3 – -2/3 = 1

1/3 * -2/3 = -2/9

1/3 / -2/3 = -1/2

-2/3 + 5 = 4+1/3

-2/3 – 5 = -5+2/3

-2/3 * 5 = -3+1/3

-2/3 / 5 = -2/15

5 + -1+1/3 = 3+2/3

5 – -1+1/3 = 6+1/3

5 * -1+1/3 = -6+2/3

5 / -1+1/3 = -3+3/4

—– Testing arithmetic between Fractions and integers

-1/2 + 4 = 3+1/2

-1/2 – 4 = -4+1/2

-1/2 * 4 = -2

-1/2 / 4 = -1/8

3 + -1/2 = 2+1/2

3 – -1/2 = 3+1/2

3 * -1/2 = -1+1/2

3 / -1/2 = -6

—– Testing shorthand arithmetic assignment on Fractions

1/6 += 4 = 4+1/6

4+1/6 -= 4 = 1/6

1/6 *= 4 = 2/3

2/3 /= 4 = 1/6

4 += -1/2 = 3+1/2

3+1/2 -= -1/2 = 4

4 *= -1/2 = -2

-2 /= -1/2 = 4

-1/2 += 5 = 4+1/2

4+1/2 -= 5 = -1/2

-1/2 *= 5 = -2+1/2

-2+1/2 /= 5 = -1/2

—– Testing shorthand arithmetic assignment using integers

-1/3 += 3 = 2+2/3

2+2/3 -= 3 = -1/3

-1/3 *= 3 = -1

-1 /= 3 = -1/3

—– Testing increment/decrement prefix and postfix

Now g = -1/3

g++ = -1/3

Now g = 2/3

++g = 1+2/3

Now g = 1+2/3

g– = 1+2/3

Now g = 2/3

–g = -1/3

Now g = -1/3