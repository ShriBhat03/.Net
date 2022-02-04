# .Net
//c# pgm for binary num//<br>
using System;<br>

namespace binary1<br>
{<br>
    class binary1<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int number, digit = 1;<br>
            Console.WriteLine("\n enter the number of lines:");<br>
            number = Convert.ToInt32(Console.ReadLine());<br>
            for (int i = 1; i <= number; i++)<br>
            {
                for (int space = number - i; space > 0; space--)<br>
                {<br>
                    Console.Write(" ");<br>
                }<br>
                for (int j = 0; j < i; j++)<br>
                {<br>
                    Console.Write(digit + "");<br>
                    digit = (digit == 1) ? 0 : 1;<br>
                }<br>
                Console.Write("\n");<br>
            }<br>
        }<br>
    }<br>
}<br>
  ++++++++++++++++++++++++++++++++++++++++++++++++++<br>

//C# pgm to implement Principle of Delegate//<br>
using System;<br>
 namespace Exercises<br>
{<br>
    class Delegates<br>
    {<br>
        delegate string UppercaseDelegate(string input);<br>
        static string UppercaseFirst(string input)<br>
        {<br>
            char[] buffer = input.ToCharArray();<br>
            buffer[0] =char.ToUpper(buffer[0]);<br>
            return new string(buffer);<br>
        }<br>
        static string UppercaseLast(string input)<br>
        {<br>
            char[] buffer =input.ToCharArray();<br>
            buffer[buffer.Length - 1] = char.ToUpper(buffer[buffer.Length - 1]);<br>
            return new string(buffer);<br>
        }<br>
        static string UppercaseALL(string input)<br>
        {<br>
            return input.ToUpper();<br>
        }<br>
        static void WriteOutput(string input, UppercaseDelegate del)<br>
        {<br>
            Console.WriteLine("iutput string:{0}", input);<br>
            Console.WriteLine("Output string:{0}", del(input));<br>
        }<br>
        static void Main()<br>
        {<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseFirst));<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseLast));<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseALL));<br>
            Console.ReadLine();<br>
        }<br>
 }<br>
}<br>
Output

:![Screenshot (2)](https://user-images.githubusercontent.com/98145090/152288860-affa08d6-4919-4cbb-8704-fe6ed52b2c28.png)<br>

++++++++++++++++++++++++++++++++++++++++++++++++++<br>

//c# pgm to generate reg num automatically//<br>
using System;<br>
namespace Exercises<br>
{<br>
    class RegisterNum<br>
    {<br>
        int regNo;<br>
        static int startNum;<br>
        static  RegisterNum()<br>
        {<br>
            startNum = 20210000;<br>
        }<br>
        RegisterNum()<br>
        {<br>
        regNo=++startNum;<br>
        }<br>
        public static void Main(String[] args)<br>
        {<br>
            for(int i=0;i<100;i++)<br>
            {<br>
                RegisterNum Student = new RegisterNum();<br>
                Console.WriteLine("student{0}:{1}", i+1, Student.regNo);<br>
                    }<br>
        }<br>
    }<br>
}<br>

Output:

![Screenshot (4)](https://user-images.githubusercontent.com/98145090/152291643-6e0d773d-ae49-4169-84ef-ae063ff9f6ae.png)<br>
++++++++++++++++++++++++++++++++++++++++++++++++++<br>
//c# pgm to print "is"//<br>
using System;<br>
namespace Exercises<br>
{<br>
    class FrequencyIS<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int count=0;<br>
            string inputString;<br>
            Console.WriteLine("\n ------Frequency of Word is-------");<br>
            Console.Write("\n Enter the input string:");<br>
            inputString=Console.ReadLine();<br>
            char[] separator ={',', ' ', '.' , '!', '\n'};<br>
            string testString=inputString.ToLower();<br>
            String[] outcomes=testString.Split(separator)<br>;
            foreach(String s in outcomes)<br>
            {<br>
                Console.WriteLine(s);<br>
                if (s=="is")<br>
                    count++;<br>
            }<br>
            Console.WriteLine("\n Number of 'is' in'"+ inputString +"' is :" + count);<br>
            }<br>
        }<br>
    }<br>
    Output:
    ![Screenshot 2022-02-03 123614](https://user-images.githubusercontent.com/98145090/152297579-4229752c-625f-47e1-96ea-78a8e838589b.png)<br>
    +++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
  //c# pgm for matrix entry//<br>
  using System;<br>
namespace Exercises<br>
{<br>
class SumOfDiagonals<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int MaxRow, MaxCol, Sum = 0;<br>
            int[,] Matrix;<br>
            Console.WriteLine("\n SUM OF DIAGONAL OF A MATRIX \n");<br>
            Console.Write("\nEnter the number of rows:");<br>
            MaxRow = Convert.ToInt32(Console.ReadLine());<br>
            Console.Write("\nEnter the number of columns:");<br>
            MaxCol = Convert.ToInt32(Console.ReadLine());<br>
            if (MaxRow != MaxCol)<br>
            {<br>
                Console.WriteLine("\nThe Dimensions entered are not of Square Matrix:");<br>
                Console.WriteLine("\nExiting the Program..");<br>
                return;<br>
            }<br>
            Matrix = new int[MaxRow, MaxCol];<br>
            for (int i = 0; i < MaxRow; i++)<br>
            {<br><br>
                for (int j = 0; j < MaxCol; j++)<br>
                {<br>
                    Console.Write("\nEnter the ({0},{l})th element of the matrix: ", (i + 1), (j + 1));<br>
                    Matrix[i, j] = Convert.ToInt32(Console.ReadLine());<br>
                }<br>
            }<br>
            Console.WriteLine("\nThe entered Matrix is:");<br>
            for (int i = 0; i < MaxRow; i++)<br>
            {
                for (int j = 0; j < MaxCol; j++)<br>
                {<br>
                    Console.Write(" " + Matrix[i, j]);<br>
                    if (i == j)<br>
                    {<br>
                        Sum += Matrix[i, j];<br>
                    }<br>
                }<br>
                Console.WriteLine();<br>
            }<br>
                Console.WriteLine("\nThe Sum of Diagonal is " + Sum);<br>
            }<br>
        }<br>
    }<br>
    Output:
    
    +++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
    //c# pgm to 2D//<br>
    using System;<br>
using System.Diagnostics;<br>
namespace array<br>
{<br>
    class Benchmarkallocation<br>
        {<br>
        const int max= 100000;<br>
    static void Main(string[] args)<br>
    {<br>
        var Arr2D = new int[100, 100];<br>
        var ArrJagged = new int[100][];<br>
        for (int i = 0; i < 100; i++)<br>
        {<br>
            ArrJagged[i] = new int[100];<br>
        }<br>
        var Stopwatch2D = Stopwatch.StartNew();<br>
        for (int i = 0; i < max; i++)<br>
        {<br>
            for (int j = 0; j < 100; j++)<br>
            {<br>
                for (int k = 0; k < 100; k++)<br>
                {<br>
                    Arr2D[j, k] = k;<br>
                }<br>
            }<br>
        }<br>
        Stopwatch2D.Stop();<br>
        var StopwatchJagged = Stopwatch.StartNew();<br>
        for (int i = 0; i < max; i++)<br>
        {<br>
            for (int j = 0; j < 100; j++)<br>
            {<br>
                for (int k = 0; k < 100; k++)<br>
                {<br>
                    ArrJagged[j][k] = k;<br>
                }<br>
            }<br>
        }<br>
        StopwatchJagged.Stop();<br>
        Console.Write("\n time taken for allocation in case of 2D array:");<br>
        Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds + "milliseconds");<br>
        Console.Write("\n time taken for allocation in case of jagged array:");<br>
        Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds + "milliseconds");<br>
    }<br>
}<br>
}<br>
Output:

![Screenshot 2022-02-04 102241](https://user-images.githubusercontent.com/98145090/152474175-653874c6-c178-48f1-913c-42d06668cd1b.png)


++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
//c# pgm for personnel detailes//<br>
using System;<br>
namespace Exercises<br>
{<br>
    class PersonalDetails<br>
    {<br>
        string name;<br>
        int age;<br>
        string gender;<br>
        public PersonalDetails(string name, int age, string gender)<br>
        {
            this.name = name;
            this.age = age;
            this.gender = gender;
        }
        public virtual void Display()
        {
            Console.WriteLine("\n-------- PERSONAL DETAILS --------\n");
            Console.WriteLine("Name : " + name);
            Console.WriteLine("Age : " + age);
            Console.WriteLine("Gender : " + gender);
        }
    }
    class CourseDetails : PersonalDetails
    {
        int regNo;
        string course;
        int semester;
        public CourseDetails(string name, int age, string gender, int regNo, string course, int semester) : base(name, age, gender)
        {
            this.regNo = regNo;
            this.course = course;
            this.semester = semester;
        }
        public override void Display()
        {
            base.Display();
            Console.WriteLine("\n-------- COURSE DETAILS --------\n");
            Console.WriteLine("Register Number : " + regNo);
            Console.WriteLine("Course : " + course);
            Console.WriteLine("Semester : " + semester);
        }
    }
    class MarksDetails : CourseDetails
    {
        int[] marks = new int[5];
        int total;
        float average;
        string grade;
        int flagFail;
        public MarksDetails(string name, int age, string gender, int regNo, string course, int semester, int[] marks) : base(name, age, gender, regNo, course, semester)
        {
            total = 0;
            for (int i = 0; i < 5; i++)
            {
                this.marks[i] = marks[i];
                total += marks[i];
                if (marks[i] < 35)
                {
                    flagFail = 1;
                }
            }
            Calculate();
        }
        private void Calculate()
        {
            average = total / 5;
            if (flagFail == 1 || average < 40)
                grade = "Fail";
            else if (average >= 70)
                grade = "Distinction";
            else if (average >= 60)
                grade = "First Class";
            else if (average >= 50)
                grade = "Second Class";
            else
                grade = "Pass Class";
        }
        public override void Display()
        {
            base.Display();
            Console.WriteLine("\n-------- MARKS DETAILS --------\n");
            Console.Write("Marks in 5 subjects: ");
            for (int i = 0; i < 5; i++)
                Console.Write(marks[i] + " ");
            Console.WriteLine();
            Console.WriteLine("Total : " + total);
            Console.WriteLine("Average : " + average);
            Console.WriteLine("Grade : " + grade);
        }
    }
    class MultiLevel
    {
        public static void Main(string[] args)
        {
            MarksDetails Student1 = new MarksDetails("Shri Bhat", 21, "Male", 20190001, "MSc", 5, new int[] { 77, 80, 98, 95, 90 });
            Student1.Display();
        }
    }
}

Output:

![Screenshot 2022-02-04 103545](https://user-images.githubusercontent.com/98145090/152475390-17adb240-d4e0-4857-ae83-9e4dd8a113ca.png)

