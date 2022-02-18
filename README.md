# .Net
1)//c# pgm for binary num//<br>
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
{ for (int space = number - i; space > 0; space--)<br>
{<br>
Console.Write(" ");<br>
}<br>
for (int j = 0; j < i; j++)<br>
{<br>
Console.Write(digit + " ");<br>
digit = (digit == 1) ? 0 : 1;<br>
}<br>
Console.Write("\n");<br>
}<br>
}<br>
}<br>
}<br>
Output:

![image](https://user-images.githubusercontent.com/98145090/152480600-26d6e300-784a-4a14-bacb-b440e14a687b.png)<br>

  ++++++++++++++++++++++++++++++++++++++++++++++++++<br>

2)//C# pgm to implement Principle of Delegate//<br>
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

3)//c# pgm to generate reg num automatically//<br>
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
4)//c# pgm to print "is"//<br>
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
  5)//c# pgm for sum of diagonal matrix entry//<br>
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
            {<br>
                for (int j = 0; j < MaxCol; j++)<br>
                {<br>
                    Console.Write("\n Enter the ({0},{1})th element of the matrix:", (i + 1), (j + 1));<br>
                    Matrix[i, j] = Convert.ToInt32(Console.ReadLine());<br>
                }<br>
            }<br>
            Console.WriteLine("\nThe entered Matrix is:");<br>
            for (int i = 0; i < MaxRow; i++)<br>
            {<br>
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
   
![Screenshot 2022-02-04 105752](https://user-images.githubusercontent.com/98145090/152479030-66e920c5-c139-4623-98d6-d2e5080989eb.png)

    
    +++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
 6)   //c# pgm to 2D//<br>
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
7)//c# pgm for personnel detailes//<br>
using System;<br>
namespace Exercises<br>
{<br>
    class PersonalDetails<br>
    {<br>
        string name;<br>
        int age;<br>
        string gender;<br>
        public PersonalDetails(string name, int age, string gender)<br>
        {<br>
            this.name = name;<br>
            this.age = age;<br>
            this.gender = gender;<br>
        }<br>
        public virtual void Display()<br>
        {<br>
            Console.WriteLine("\n-------- PERSONAL DETAILS --------\n");<br>
            Console.WriteLine("Name : " + name);<br>
            Console.WriteLine("Age : " + age);<br>
            Console.WriteLine("Gender : " + gender);<br>
        }<br>
    }<br>
    class CourseDetails : PersonalDetails<br>
    {<br>
        int regNo;<br>
        string course;<br>
        int semester;<br>
        public CourseDetails(string name, int age, string gender, int regNo, string course, int semester) : base(name, age, gender)<br>
        {<br>
            this.regNo = regNo;<br>
            this.course = course;<br>
            this.semester = semester;<br>
        }<br>
        public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("\n-------- COURSE DETAILS --------\n");<br>
            Console.WriteLine("Register Number : " + regNo);<br>
            Console.WriteLine("Course : " + course);<br>
            Console.WriteLine("Semester : " + semester);<br>
        }<br>
    }<br>
    class MarksDetails : CourseDetails<br>
    {<br>
        int[] marks = new int[5];<br>
        int total;<br>
        float average;<br>
        string grade;<br>
        int flagFail;<br>
        public MarksDetails(string name, int age, string gender, int regNo, string course, int semester, int[] marks) : base(name, age, gender, regNo, course, semester)<br>
        {<br>
            total = 0;<br>
            for (int i = 0; i < 5; i++)<br>
            {<br>
                this.marks[i] = marks[i];<br>
                total += marks[i];<br>
                if (marks[i] < 35)<br>
                {<br>
                    flagFail = 1;<br>
                }<br>
            }<br>
            Calculate();<br>
        }<br>
        private void Calculate()<br>
        {<br>
            average = total / 5;<br>
            if (flagFail == 1 || average < 40)<br>
                grade = "Fail";<br>
            else if (average >= 70)<br>
                grade = "Distinction";<br>
            else if (average >= 60)<br>
                grade = "First Class";<br>
            else if (average >= 50)<br>
                grade = "Second Class";<br>
            else<br>
                grade = "Pass Class";<br>
        }<br>
        public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("\n-------- MARKS DETAILS --------\n");<br>
            Console.Write("Marks in 5 subjects: ");<br>
            for (int i = 0; i < 5; i++)<br>
                Console.Write(marks[i] + " ");<br>
            Console.WriteLine();<br>
            Console.WriteLine("Total : " + total);<br>
            Console.WriteLine("Average : " + average);<br>
            Console.WriteLine("Grade : " + grade);<br>
        }<br>
    }<br>
    class MultiLevel<br>
    {<br>
        public static void Main(string[] args)<br>
        {<br>
            MarksDetails Student1 = new MarksDetails("Shri Bhat", 21, "Male", 20190001, "MSc", 5, new int[] { 77, 80, 98, 95, 90 });<br>
            Student1.Display();<br>
        }<br>
    }<br>
}<br>

Output:

![Screenshot 2022-02-04 103545](https://user-images.githubusercontent.com/98145090/152475390-17adb240-d4e0-4857-ae83-9e4dd8a113ca.png)<br>
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
8) //c# pgm to gray code//<br>
using System;<br>

namespace Exercises<br>
{<br>
    class GrayCode<br>
    {<br>
        static int getGray(int n)<br>
        {<br>
            return n^(n>>1);<br>
        }<br>
        static void Main(string[] args)<br>
        {<br>
            int InputNum, GrayNum;<br>
            Console.Write("\nEnter the decimal number:");<br>
            InputNum = Convert.ToInt32(Console.ReadLine());<br>
            Console.Write("\n Binary equivalent of {0} : {1}",InputNum,Convert.ToString(InputNum,2));<br>
<br>
            GrayNum = getGray(InputNum);<br>
            Console.Write("\n GrayCode equivalent of {0} : {1}", InputNum, Convert.ToString(GrayNum, 2));<br>
        }<br>
    }<br>
}<br>
 Output:
 ![image](https://user-images.githubusercontent.com/98145090/152478001-3c867ff9-0a0f-43ff-b882-8024d901d0c5.png)

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
9) //c# pgm to addition of 2 boxes//<br>
using System;<br>
<br>
namespace Exercises<br>
{<br>
    class Box<br>
    {<br>
        float width;<br>
        float height;<br>
        float length;<br>
        public float Volume<br>
        {<br>
            get { return width * height * length; }<br>
        }<br>
        public Box(float width, float height, float length)<br>
        {<br>
            this.width = width;<br>
            this.height = height;<br>
            this.length = length;<br>
        }<br>
        public static float operator +(Box box1, Box box2)<br>
        {<br>
            return box1.Volume + box2.Volume;<br>
        }<br>
        public override string ToString()<br>
        {<br>
            return "box with width " + width + ",height " + height + " and length " + length;<br>
        }<br>
    }<br>
        class OperatorOverloading<br>
        {<br>
            public static void Main()<br>
            {<br>
                Box box1 = new Box(10, 20, 30);<br>
                Box box2 = new Box(25, 32, 15);<br>
                Console.WriteLine("Volume of {0} is {1}", box1, box1.Volume);<br>
                Console.WriteLine("Volume of {0} is {1}", box2, box2.Volume);<br>
                Console.WriteLine("Volume after adding boxes: {0}",box1+box2);<br>
            }<br>
        }<br>
}<br>

Output:
![image](https://user-images.githubusercontent.com/98145090/152478575-9923f5ea-f1b6-4b71-a743-f10f4d768db8.png)


++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
10//c# pgm for amicable numbers//<br>
using System;<br>
namespace Exercises<br>
{<br>
    class AmicableNumber<br>
    {<br>
        static void Main(String[] args)<br>
        {<br>
            int num1,num2,sum1=0,sum2=0;<br>
            Console.WriteLine("\n........AMICABLE NUMBERS........\n");<br>
            Console.Write("\nEnter the First Number:");<br>
            num1 = Convert.ToInt32(Console.ReadLine());<br>
            Console.Write("\nEnter the Second Number:");<br>
            num2 = Convert.ToInt32(Console.ReadLine());<br>
            for (int i = 1; i < num1; i++)<br>
            {<br>
                if (num1 % i == 0)<br>
                {<br>
                    sum1 += i;<br>
                }<br>
            }<br>
            for (int i = 1; i < num2; i++)<br>
            {<br>
                if (num2 % i == 0)<br>
                {<br>
                    sum2 += i;<br>
                }<br>
            }<br>
            if(num1 == sum2 && num2 == sum1)<br>
            {<br>
                Console.WriteLine("\nThe numbers {0} and {1} are amicable.", num1, num2);<br>
            }<br>
            else<br>
            {<br>
                Console.WriteLine("\nThe numbers {0} and {1} are not amicable.", num1, num2);<br>
            }<br>
        }<br>
    }<br>
}<br>
Output:
![image](https://user-images.githubusercontent.com/98145090/152478908-4e9365b4-913e-4bac-a437-62ab3104fbb7.png)

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
11)//c# pgm to create a file , Check the existence of a file//<br>
using System;<br>
using System.IO;<br>
namespace Exercise<br>
{<br>
    class FileRead<br>
    {<br>
        public static void Main()<br>
        {<br>
            string fileName;<br>
            while (true)<br>
            {<br>
                Console.WriteLine("\n.......MENU......\n");<br>
                Console.WriteLine("\n1.Create a File");<br>
                Console.WriteLine("\n2.Existence of the File");<br>
                Console.WriteLine("\n3.Read the contents of the File");<br>
                Console.WriteLine("\n4.Exit");<br>
                Console.WriteLine("\nEnter your choice:");<br>
                int ch = int.Parse(Console.ReadLine());<br>
                switch (ch)<br>
                {<br>
                    case 1:<br>
                        Console.Write("\nEnter the file name to create:");<br>
                        fileName = Console.ReadLine();<br>
                        Console.WriteLine("\nWrite the Contents to the File:\n");<br>
                        string r = Console.ReadLine();<br>
                        using (StreamWriter fileStr = File.CreateText(fileName))<br>
                        {<br>
                            fileStr.WriteLine(r);<br>
                        }<br>
                        Console.WriteLine("File is Created...");<br>
                        break;<br>
                    case 2:<br>
                        Console.Write("\nEnter the file name:");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            Console.WriteLine("File exits...");<br>
                        }<br>
                        else<br>
                        {<br>
                            Console.WriteLine("File does not exits in the current directory!");<br>
                        }<br>
                        break;<br>
                    case 3:<br>
                        Console.Write("Enter the file name to read the contents:\n");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            using (StreamReader sr = File.OpenText(fileName))<br>
                            {<br>
                                string s = "";<br>
                                Console.WriteLine(" Here is the content of the file : ");<br>
                                while ((s = sr.ReadLine()) != null)<br>
                                {<br>
                                    Console.WriteLine(s);<br>
                                }<br>
                                Console.WriteLine("");<br>
                            }<br>
                        }<br>
                        else<br>
                        {<br>
                            Console.WriteLine("File does not exists");<br>
                        }<br>
                        break;<br>
                    case 4:<br>
                        Console.WriteLine("\n Exiting...");<br>
                        return;<br>
                    default:<br>
                        Console.WriteLine("\n Invalid choice");<br>
                        break;<br>
            }<br>
        }<br>
    }<br>
}<br>
Output:<br>
1-<br>![exis 1](https://user-images.githubusercontent.com/98145090/154413141-56c36639-0ef7-4daf-ae17-a00694399718.png)<br>
2-<br>![exis 2](https://user-images.githubusercontent.com/98145090/154413878-c6c32399-f59d-405d-bba0-72eb00686c25.png)<br>
3-<br>![exis 3](https://user-images.githubusercontent.com/98145090/154413955-c3c109d8-368f-4bfa-887d-04f73fef2609.png)<br>
4-<br>![exis 4](https://user-images.githubusercontent.com/98145090/154413972-0ab90235-a9d4-47f6-b8cb-7f73529fd09b.png)<br>
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ <br>
12)//C# Program to Perform File Comparison.//<br>
using System;<br>
using System.IO;<br>
namespace Exercises<br>
{<br>
 class FileRead<br>
 {<br>
 public static void Main()<br>
 {<br>
 string file1;<br>
 string file2;<br>
 Console.Write("Enter the first file path:");<br>
 file1 = Console.ReadLine();<br>
 Console.Write("Enter the second file path:");<br>
 file2 = Console.ReadLine();<br>
 if (!File.Exists(file1))<br>
 {<br>
 Console.WriteLine("First file does not exist!");<br>
 }<br>
 else if (!File.Exists(file2))<br>
 {<br>
 Console.WriteLine("Second file does not exist!");<br>
 }<br>
 else if (File.ReadAllText(file1) == File.ReadAllText(file2))<br>
 {<br>
 Console.WriteLine("Both files contain the same content");<br>
 }<br>
 else<br>
 {<br>
 Console.WriteLine("Contents of files are not same");<br>
 }<br>
 }<br>
 }<br>
}<br>


Output:<br>
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
13)//C# Program to Implement IComparable Interface// <br>
 using System;<br>
namespace Exercises<br>
{<br>
    class Fraction : IComparable<br>
    {<br>
        int z, n;<br>
        public Fraction(int z, int n)<br>
        {<br>
            this.z = z;<br>
            this.n = n;<br>
        }<br>
        public static Fraction operator +(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n);<br>
        }<br>
        public static Fraction operator *(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.z, a.n * b.n);<br>
        }<br>
        public int CompareTo(object obj)<br>
        {<br>
            Fraction f = (Fraction)obj;<br>
            if ((float)z / n < (float)f.z / f.n)<br>
                return -1;<br>
            else if ((float)z / n > (float)f.z / f.n)<br>
                return 1;<br>
            else<br>
                return 0;<br>
        }<br>
        public override string ToString()<br>
        {<br>
            return z + "/" + n;<br>
        }<br>
    }<br>
    class ICompInterface<br>
    {<br>
        public static void Main()<br>
        {<br>
        Fraction[] a = {<br>
                        new Fraction(5,2),<br>
                        new Fraction(29,6),<br>
                        new Fraction(4,5),<br>
                        new Fraction(10,8),<br>
                        new Fraction(34,7)<br>
 };<br>
            Array.Sort(a);<br>
            Console.WriteLine("Implementing the IComparable Interface in " + "Displaying  Fractions: ");<br>
        foreach (Fraction f in a)<br>
            {<br>
                Console.WriteLine(f + " ");<br>
            }<br>
            Console.WriteLine();<br>
            Console.ReadLine();<br>
        }<br>
    }<br>
}<br>

Output:![image](https://user-images.githubusercontent.com/98145090/154629265-1abbcf74-258d-4b4e-99c1-e16ea8c4897c.png)<br>
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
14)//c# pgm to create Thread Pools//<br>
using System;<br>
using System.Threading;<br>
namespace Exercises<br>
{<br>
    class ThreadPoolProg<br>
    {<br>
        public void ThreadFun1(object obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
            {<br>
                Console.WriteLine("Thread1 is executing");<br>
            }<br>
        }<br>
        public void ThreadFun2(object obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
                Console.WriteLine("Thread 2 is executing");<br>
        }<br>
        public static void Main()<br>
        {<br>
            ThreadPoolProg TP = new ThreadPoolProg();<br>
            for (int i = 0; i < 2; i++)<br>
            {<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1));<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));<br>
            }<br>
            Console.ReadKey();<br>
        }<br>
    }<br>
}<br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145090/154628176-9235a479-9d98-4e8f-adc4-81da971190eb.png)<br>

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
15 //c# pgm to demonstrate error handling using try , catch and finally block//<br>
using System;<br>
namespace Exercises<br>
{<br>
    class ExceptionHandling<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            Age a = new Age();<br>
            try<br>
            {<br>
                a.displayAge();<br>
            }<br>
            catch (AgeIsNegativeException e)<br>
            {<br>
                Console.WriteLine("AgeIsNegativeException: {0}", e.Message);<br>
            }<br>
            finally<br>
            {<br>
                Console.WriteLine("Execution of Finally block is done.");<br>
            }<br>
        }<br>
    }<br>
}<br>
public class AgeIsNegativeException : Exception<br>
{<br>
    public AgeIsNegativeException(string message) : base(message)<br>
    {<br>
    }<br>
}<br>
public class Age<br>
{<br>
    int age = -5;<br>
    public void displayAge()<br>
    {<br>
        if (age < 0)<br>
        {<br>
            throw (new AgeIsNegativeException("Age cannot be negative"));<br>
        }<br>
        else<br>
        {<br>
            Console.WriteLine("Age is: {0}", age);<br>
        }<br>
    }<br>
}<br>
Output:![image](https://user-images.githubusercontent.com/98145090/154629983-3f6abf48-c40e-4a0f-a26e-f30e1f890abf.png)<br>
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
