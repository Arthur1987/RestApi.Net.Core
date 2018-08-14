# RestApi.Net.Core
.NET core rest api Library
Code example

    class Program
    {
        public static async Task Main(string[] args)
        {
            using (RestApiClient client = new RestApiClient("https://httpbin.org"))
            {
                var result = await client.GetAsync<Response>("get");
                Console.WriteLine($"Origin is {result.Origin} Url is {result.Url}");
            }
        }
    }

    public class Response
    {
        public string Origin { get; set; }

        public string Url { get; set; }
    }
