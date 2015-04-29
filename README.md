Example1 - string concat and number calculate:

string code = "2.ToString()+(4*2)"; // C# code

Func<string> func = ExpressionParser.Compile<Func<string>>(code); // compile code

string result = func(); // result = "28"


Example2 - input parameter:

Delegate dele = ExpressionParser.Compile("(int m)=>-m");

var result = (int)dele.DynamicInvoke(10); // result = -10


Example3 - access property in anonymous type:

//using Zhucai.LambdaParser.ObjectDynamicExtension;

object obj = new { Name = "zhangsan", Id = 18 }; // maybe get [obj] from method return value

int result = obj.E<int>("Id"); // result = 18

