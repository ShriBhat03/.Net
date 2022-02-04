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

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>


