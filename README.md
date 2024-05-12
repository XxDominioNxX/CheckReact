https://drive.google.com/file/d/1j7JnHd1_gxVL0_AYBmpxayCeivLwd1TN/view?usp=drive_link


static void Main(string[] args)
{
    var aa = Tests().Result;
    Console.WriteLine("Greeting: ");
    Console.WriteLine("Press any key to exit...");
    Console.ReadKey();
}

private static async Task<string> Tests()
{
    var channel = new Channel("localhost:5104", ChannelCredentials.Insecure);
    var client = new Greeter.GreeterClient(channel);
    var reply = await client.SayHelloAsync(
                      new HelloRequest { Name = "GreeterClient"});
    return reply.Message;
}
