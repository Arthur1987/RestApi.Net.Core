# RestApi.Net.Core
.NET core rest api is simple library to send HTTP request, it was implemented generic, support JSON(Newtonsoft.Json) and XML serialization and deserialization.

Here is code example

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
