---


---

<h2 id="python-api-get-and-post-examples">Python API GET and POST Examples</h2>
<p><em>Athor: Islom Mamatov</em></p>
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

