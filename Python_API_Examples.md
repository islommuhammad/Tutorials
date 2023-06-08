---


---

<h2 id="python-api-get-and-post-examples">Python API GET and POST Examples</h2>
<p><em>Athor: Islom Mamatov</em></p>
<p><strong>Here’s a step-by-step tutorial to help you get started:</strong></p>
<p><strong>Step 1: Understand APIs</strong><br>
An API (Application Programming Interface) allows different software applications to communicate and interact with each other. APIs provide a set of rules and protocols for requesting and exchanging data between systems.</p>
<p><strong>Step 2: Choose an API</strong><br>
Decide which API you want to work with. There are various APIs available for different purposes such as weather data, social media integration, financial data, etc. For this tutorial, let’s use the OpenWeatherMap API, which provides weather-related information.</p>
<p><strong>Step 3: Get an API Key</strong><br>
Many APIs require an API key for authentication and tracking usage. Sign up on the API provider’s website (OpenWeatherMap in this case) and obtain an API key. Make sure to keep your API key secure and avoid sharing it publicly.</p>
<p><strong>Step 4: Install Requests Library</strong><br>
The Requests library is widely used for making HTTP requests in Python. Install it by running the following command in your terminal:</p>
<pre><code>pip install requests
</code></pre>
<p><strong>Step 5: Import Required Libraries</strong><br>
In your Python script, import the necessary libraries:</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token keyword">import</span> requests
</code></pre>
<p><strong>Step 6: Make API Requests</strong><br>
Use the <code>requests</code> library to send HTTP requests to the API. Here’s an example that retrieves the current weather for a specific city using the OpenWeatherMap API:</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token keyword">import</span> requests

api_key <span class="token operator">=</span> <span class="token string">'YOUR_API_KEY'</span>
city <span class="token operator">=</span> <span class="token string">'London'</span>

url <span class="token operator">=</span> f<span class="token string">'http://api.openweathermap.org/data/2.5/weather?q={city}&amp;appid={api_key}'</span>

response <span class="token operator">=</span> requests<span class="token punctuation">.</span>get<span class="token punctuation">(</span>url<span class="token punctuation">)</span>
data <span class="token operator">=</span> response<span class="token punctuation">.</span>json<span class="token punctuation">(</span><span class="token punctuation">)</span>

<span class="token keyword">print</span><span class="token punctuation">(</span>data<span class="token punctuation">)</span>
</code></pre>
<p>Replace <code>'YOUR_API_KEY'</code> with your actual API key. You can also modify the <code>'London'</code> variable to fetch weather data for a different city.</p>
<p>Step 7: Process the Response<br>
The API response will be in JSON format. You can extract the required information from the response data and use it as needed. For example, to retrieve the temperature from the response:</p>
<pre class=" language-python"><code class="prism  language-python">temperature <span class="token operator">=</span> data<span class="token punctuation">[</span><span class="token string">'main'</span><span class="token punctuation">]</span><span class="token punctuation">[</span><span class="token string">'temp'</span><span class="token punctuation">]</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>f<span class="token string">'Temperature: {temperature} Kelvin'</span><span class="token punctuation">)</span>
</code></pre>
<p>Step 8: Error Handling<br>
API requests can sometimes fail due to network issues or incorrect parameters. Implement error handling in your code to handle such situations gracefully. For example:</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token keyword">if</span> response<span class="token punctuation">.</span>status_code <span class="token operator">==</span> <span class="token number">200</span><span class="token punctuation">:</span>
    data <span class="token operator">=</span> response<span class="token punctuation">.</span>json<span class="token punctuation">(</span><span class="token punctuation">)</span>
    <span class="token comment"># Process the data</span>
<span class="token keyword">else</span><span class="token punctuation">:</span>
    <span class="token keyword">print</span><span class="token punctuation">(</span>f<span class="token string">'Request failed with status code: {response.status_code}'</span><span class="token punctuation">)</span>
</code></pre>
<p>That’s it! You now have a basic understanding of how to work with APIs in Python. Remember to refer to the API documentation for specific details on the available endpoints, parameters, and data formats.</p>
<h2 id="here-are-more-examples">Here are more examples</h2>
<p><strong>Example 1: GET Request</strong><br>
In this example, we’ll use the Chuck Norris API to fetch a random joke. The Chuck Norris API provides various endpoints to retrieve Chuck Norris jokes.</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token keyword">import</span> requests

url <span class="token operator">=</span> <span class="token string">'https://api.chucknorris.io/jokes/random'</span>

response <span class="token operator">=</span> requests<span class="token punctuation">.</span>get<span class="token punctuation">(</span>url<span class="token punctuation">)</span>
data <span class="token operator">=</span> response<span class="token punctuation">.</span>json<span class="token punctuation">(</span><span class="token punctuation">)</span>

joke <span class="token operator">=</span> data<span class="token punctuation">[</span><span class="token string">'value'</span><span class="token punctuation">]</span>
<span class="token keyword">print</span><span class="token punctuation">(</span>joke<span class="token punctuation">)</span>
</code></pre>
<p>The above code sends a GET request to the Chuck Norris API endpoint to fetch a random joke. The response is then parsed as JSON, and the joke is extracted from the response data.</p>
<p><strong>Example 2: POST Request</strong><br>
In this example, we’ll use the JSONPlaceholder API, a fake online REST API for testing and prototyping. We’ll create a new post using the POST method.</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token keyword">import</span> requests

url <span class="token operator">=</span> <span class="token string">'https://jsonplaceholder.typicode.com/posts'</span>

data <span class="token operator">=</span> <span class="token punctuation">{</span>
    <span class="token string">'title'</span><span class="token punctuation">:</span> <span class="token string">'New Post'</span><span class="token punctuation">,</span>
    <span class="token string">'body'</span><span class="token punctuation">:</span> <span class="token string">'This is the body of the new post.'</span><span class="token punctuation">,</span>
    <span class="token string">'userId'</span><span class="token punctuation">:</span> <span class="token number">1</span>
<span class="token punctuation">}</span>

response <span class="token operator">=</span> requests<span class="token punctuation">.</span>post<span class="token punctuation">(</span>url<span class="token punctuation">,</span> json<span class="token operator">=</span>data<span class="token punctuation">)</span>
new_post <span class="token operator">=</span> response<span class="token punctuation">.</span>json<span class="token punctuation">(</span><span class="token punctuation">)</span>

<span class="token keyword">print</span><span class="token punctuation">(</span>new_post<span class="token punctuation">)</span>
</code></pre>
<p>The above code sends a POST request to the JSONPlaceholder API’s <code>/posts</code> endpoint with a JSON payload containing the title, body, and userId of the new post. The response contains the newly created post, which is then printed to the console.</p>
<p>Remember to refer to the API documentation for specific details on the endpoints, request parameters, and data formats for the APIs you are working with.</p>
<p><strong>Here’s an example using a token for authentication with the GitHub API:</strong></p>
<pre class=" language-python"><code class="prism  language-python"><span class="token keyword">import</span> requests

url <span class="token operator">=</span> <span class="token string">'https://api.github.com/user/repos'</span>
token <span class="token operator">=</span> <span class="token string">'YOUR_GITHUB_TOKEN'</span>

headers <span class="token operator">=</span> <span class="token punctuation">{</span>
    <span class="token string">'Authorization'</span><span class="token punctuation">:</span> f<span class="token string">'Token {token}'</span>
<span class="token punctuation">}</span>

response <span class="token operator">=</span> requests<span class="token punctuation">.</span>get<span class="token punctuation">(</span>url<span class="token punctuation">,</span> headers<span class="token operator">=</span>headers<span class="token punctuation">)</span>
repos <span class="token operator">=</span> response<span class="token punctuation">.</span>json<span class="token punctuation">(</span><span class="token punctuation">)</span>

<span class="token keyword">for</span> repo <span class="token keyword">in</span> repos<span class="token punctuation">:</span>
    <span class="token keyword">print</span><span class="token punctuation">(</span>repo<span class="token punctuation">[</span><span class="token string">'name'</span><span class="token punctuation">]</span><span class="token punctuation">)</span>
</code></pre>
<p>In the code above, we’re making a GET request to the GitHub API to fetch the repositories of the authenticated user. Replace <code>'YOUR_GITHUB_TOKEN'</code> with your actual GitHub personal access token.</p>
<p>We set the token as the value for the <code>Authorization</code> header in the request headers. This header is required for authentication with the GitHub API, and the token is prefixed with the word “Token” before passing it.</p>
<p>The response contains a JSON array of repositories, which we iterate over and print the names of the repositories.</p>
<p>Make sure to generate and use your own personal access token with the necessary permissions when working with authenticated APIs. The method and format for passing the token may vary depending on the specific API you are using, so consult the API documentation for the correct approach.</p>

