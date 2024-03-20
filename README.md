# YouTube-autoreply

<div class="page"><div class="page-number">Page 1 of 1</div><h1 class="title" data-reader-unique-id="titleElement">How to Extract YouTube Comments Using Youtube API – Python</h1>
                                                                <p data-reader-unique-id="1"><strong data-reader-unique-id="2">Prerequisite:</strong> <a href="https://www.geeksforgeeks.org/youtube-data-api-set-1/" data-reader-unique-id="3"><strong data-reader-unique-id="4">YouTube API</strong></a></p>
<p data-reader-unique-id="5">Google provides a large set of API’s for the developer to choose from. Each and every service provided by Google has an associated API. Being one of them, YouTube Data API is very simple to use provides features like –</p>
<ul data-reader-unique-id="7">
<li data-reader-unique-id="8">Search for videos</li>
<li data-reader-unique-id="9">Handle videos like retrieve information about a video, insert a video, delete a video etc.</li>
<li data-reader-unique-id="10">Handle Subscriptions like lists all the subscriptions, insert or delete a subscription etc.</li>
</ul>
<p data-reader-unique-id="11">In this article, we will discuss How to Extract YouTube Comments and reply using Google YouTube API in Python.</p>
<p data-reader-unique-id="12"><strong data-reader-unique-id="13">Understand step by step implementation:-</strong></p>
<ul data-reader-unique-id="41">
<li data-reader-unique-id="42">Retrieve YouTube Video Results
<ul data-reader-unique-id="43">
<li data-reader-unique-id="44">Here we will use <strong data-reader-unique-id="45">commentThreads, list, execute </strong>method, it will give the list of comment and replies</li>
<li data-reader-unique-id="46">Inside <strong data-reader-unique-id="47">list </strong>method, pass snippet and replies in <strong data-reader-unique-id="48">part </strong>property and in <strong data-reader-unique-id="49">videoId </strong>property pass video id of video URL</li>
</ul>
</li>
</ul>
<div data-reader-unique-id="50">
<div class="clear" data-reader-unique-id="51"><div data-reader-unique-id="52"><ul role="tablist" data-reader-unique-id="53"><li aria-controls="tablist1-panel1" role="tab" tabindex="0" data-reader-unique-id="54">Python3</li></ul>

<div aria-hidden="false" role="tabpanel" aria-labelledby="tablist1-tab1" data-reader-unique-id="55">

<div data-reader-unique-id="56">
<div data-reader-unique-id="57">
<div data-reader-unique-id="58">
<div data-reader-unique-id="59">
<div title="Run and Edit" data-reader-unique-id="60">
                                    <i title="Copy Code" data-reader-unique-id="61"></i>





<p data-reader-unique-id="64">                                    
                                    <i title="Light Mode" data-reader-unique-id="65"></i>
                                    
                                </p></div>
</div>
</div>
</div>
<div data-reader-unique-id="66">
<div data-reader-unique-id="67">
<div class="scrollable" style=""><table border="0" cellpadding="0" cellspacing="0" data-reader-unique-id="68">
<tbody data-reader-unique-id="69">
<tr data-reader-unique-id="70">
<td data-reader-unique-id="71">
<div data-reader-unique-id="72">

<p data-reader-unique-id="74"><code data-reader-unique-id="75">youtube </code><code data-reader-unique-id="76">=</code> <code data-reader-unique-id="77">build(</code><code data-reader-unique-id="78">'youtube'</code><code data-reader-unique-id="79">,</code><code data-reader-unique-id="80">'v3'</code><code data-reader-unique-id="81">,</code></p>
<p data-reader-unique-id="82"><code data-reader-unique-id="83">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="84">developerKey</code><code data-reader-unique-id="85">=</code><code data-reader-unique-id="86">"Enter API Key"</code><code data-reader-unique-id="87">)</code></p>


<p data-reader-unique-id="90"><code data-reader-unique-id="91">video_response</code><code data-reader-unique-id="92">=</code><code data-reader-unique-id="93">youtube.commentThreads().</code><code data-reader-unique-id="94">list</code><code data-reader-unique-id="95">(</code></p>
<p data-reader-unique-id="96"><code data-reader-unique-id="97">&nbsp;&nbsp;</code><code data-reader-unique-id="98">part</code><code data-reader-unique-id="99">=</code><code data-reader-unique-id="100">'snippet,replies'</code><code data-reader-unique-id="101">,</code></p>
<p data-reader-unique-id="102"><code data-reader-unique-id="103">&nbsp;&nbsp;</code><code data-reader-unique-id="104">videoId</code><code data-reader-unique-id="105">=</code><code data-reader-unique-id="106">"Enter Video ID"</code></p>
<p data-reader-unique-id="107"><code data-reader-unique-id="108">).execute()</code></p>
</div>
</td>
</tr>
</tbody>
</table></div>
</div></div>

</div>

</div></div></div></div>
<ul data-reader-unique-id="109">
<li data-reader-unique-id="110">Iterate through each Video Response and fetch comments and replies
<ul data-reader-unique-id="111">
<li data-reader-unique-id="112">The data comes in dictionary format, each comment data has reply count number, if reply count number is zero means no reply on that comment</li>
<li data-reader-unique-id="113">if count is greater than zero then we are iterating each reply and get text.</li>
<li data-reader-unique-id="114"><strong data-reader-unique-id="115">nextPageToken </strong>contain the next data, here we are checking if nextPageToken has no value it means value is None, loop end, else loop will continue.</li>
</ul>
</li>
</ul>
<p data-reader-unique-id="116"><strong data-reader-unique-id="117">Below is the full implementation:</strong></p>
<div data-reader-unique-id="118">
<div class="clear" data-reader-unique-id="119"><div data-reader-unique-id="120"><ul role="tablist" data-reader-unique-id="121"><li aria-controls="tablist2-panel1" role="tab" tabindex="0" data-reader-unique-id="122">Python3</li></ul>

<div aria-hidden="false" role="tabpanel" aria-labelledby="tablist2-tab1" data-reader-unique-id="123">

<div data-reader-unique-id="124">
<div data-reader-unique-id="125">
<div data-reader-unique-id="126">
<div data-reader-unique-id="127">
<div title="Run and Edit" data-reader-unique-id="128">
                                    <i title="Copy Code" data-reader-unique-id="129"></i>





<p data-reader-unique-id="132">                                    
                                    <i title="Light Mode" data-reader-unique-id="133"></i>
                                    
                                </p></div>
</div>
</div>
</div>
<div data-reader-unique-id="134">
<div data-reader-unique-id="135">
<div class="scrollable" style=""><table border="0" cellpadding="0" cellspacing="0" data-reader-unique-id="136">
<tbody data-reader-unique-id="137">
<tr data-reader-unique-id="138">
<td data-reader-unique-id="139">
<div data-reader-unique-id="140">
<p data-reader-unique-id="141"><code data-reader-unique-id="142">from</code> <code data-reader-unique-id="143">googleapiclient.discovery </code><code data-reader-unique-id="144">import</code> <code data-reader-unique-id="145">build</code></p>

<p data-reader-unique-id="147"><code data-reader-unique-id="148">api_key </code><code data-reader-unique-id="149">=</code> <code data-reader-unique-id="150">'API KEY'</code></p>

<p data-reader-unique-id="152"><code data-reader-unique-id="153">def</code> <code data-reader-unique-id="154">video_comments(video_id):</code></p>
<p data-reader-unique-id="155"><code data-reader-unique-id="156">&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="157"><code data-reader-unique-id="158">&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="159">replies </code><code data-reader-unique-id="160">=</code> <code data-reader-unique-id="161">[]</code></p>

<p data-reader-unique-id="163"><code data-reader-unique-id="164">&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="165"><code data-reader-unique-id="166">&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="167">youtube </code><code data-reader-unique-id="168">=</code> <code data-reader-unique-id="169">build(</code><code data-reader-unique-id="170">'youtube'</code><code data-reader-unique-id="171">, </code><code data-reader-unique-id="172">'v3'</code><code data-reader-unique-id="173">,</code></p>
<p data-reader-unique-id="174"><code data-reader-unique-id="175">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="176">developerKey</code><code data-reader-unique-id="177">=</code><code data-reader-unique-id="178">api_key)</code></p>

<p data-reader-unique-id="180"><code data-reader-unique-id="181">&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="182"><code data-reader-unique-id="183">&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="184">video_response</code><code data-reader-unique-id="185">=</code><code data-reader-unique-id="186">youtube.commentThreads().</code><code data-reader-unique-id="187">list</code><code data-reader-unique-id="188">(</code></p>
<p data-reader-unique-id="189"><code data-reader-unique-id="190">&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="191">part</code><code data-reader-unique-id="192">=</code><code data-reader-unique-id="193">'snippet,replies'</code><code data-reader-unique-id="194">,</code></p>
<p data-reader-unique-id="195"><code data-reader-unique-id="196">&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="197">videoId</code><code data-reader-unique-id="198">=</code><code data-reader-unique-id="199">video_id</code></p>
<p data-reader-unique-id="200"><code data-reader-unique-id="201">&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="202">).execute()</code></p>

<p data-reader-unique-id="204"><code data-reader-unique-id="205">&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="206"><code data-reader-unique-id="207">&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="208">while</code> <code data-reader-unique-id="209">video_response:</code></p>
<p data-reader-unique-id="210"><code data-reader-unique-id="211">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code>&nbsp;</p>
<p data-reader-unique-id="212"><code data-reader-unique-id="213">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="214"><code data-reader-unique-id="215">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="216"><code data-reader-unique-id="217">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="218">for</code> <code data-reader-unique-id="219">item </code><code data-reader-unique-id="220">in</code> <code data-reader-unique-id="221">video_response[</code><code data-reader-unique-id="222">'items'</code><code data-reader-unique-id="223">]:</code></p>
<p data-reader-unique-id="224"><code data-reader-unique-id="225">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code>&nbsp;</p>
<p data-reader-unique-id="226"><code data-reader-unique-id="227">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="228"><code data-reader-unique-id="229">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="230">comment </code><code data-reader-unique-id="231">=</code> <code data-reader-unique-id="232">item[</code><code data-reader-unique-id="233">'snippet'</code><code data-reader-unique-id="234">][</code><code data-reader-unique-id="235">'topLevelComment'</code><code data-reader-unique-id="236">][</code><code data-reader-unique-id="237">'snippet'</code><code data-reader-unique-id="238">][</code><code data-reader-unique-id="239">'textDisplay'</code><code data-reader-unique-id="240">]</code></p>
<p data-reader-unique-id="241"><code data-reader-unique-id="242">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code>&nbsp;</p>
<p data-reader-unique-id="243"><code data-reader-unique-id="244">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="245"><code data-reader-unique-id="246">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="247">replycount </code><code data-reader-unique-id="248">=</code> <code data-reader-unique-id="249">item[</code><code data-reader-unique-id="250">'snippet'</code><code data-reader-unique-id="251">][</code><code data-reader-unique-id="252">'totalReplyCount'</code><code data-reader-unique-id="253">]</code></p>

<p data-reader-unique-id="255"><code data-reader-unique-id="256">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="257"><code data-reader-unique-id="258">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="259">if</code> <code data-reader-unique-id="260">replycount&gt;</code><code data-reader-unique-id="261">0</code><code data-reader-unique-id="262">:</code></p>
<p data-reader-unique-id="263"><code data-reader-unique-id="264">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code>&nbsp;</p>
<p data-reader-unique-id="265"><code data-reader-unique-id="266">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="267"><code data-reader-unique-id="268">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="269">for</code> <code data-reader-unique-id="270">reply </code><code data-reader-unique-id="271">in</code> <code data-reader-unique-id="272">item[</code><code data-reader-unique-id="273">'replies'</code><code data-reader-unique-id="274">][</code><code data-reader-unique-id="275">'comments'</code><code data-reader-unique-id="276">]:</code></p>
<p data-reader-unique-id="277"><code data-reader-unique-id="278">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code>&nbsp;</p>
<p data-reader-unique-id="279"><code data-reader-unique-id="280">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="281"><code data-reader-unique-id="282">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="283">reply </code><code data-reader-unique-id="284">=</code> <code data-reader-unique-id="285">reply[</code><code data-reader-unique-id="286">'snippet'</code><code data-reader-unique-id="287">][</code><code data-reader-unique-id="288">'textDisplay'</code><code data-reader-unique-id="289">]</code></p>
<p data-reader-unique-id="290"><code data-reader-unique-id="291">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code>&nbsp;</p>
<p data-reader-unique-id="292"><code data-reader-unique-id="293">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="294"><code data-reader-unique-id="295">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="296">replies.append(reply)</code></p>

<p data-reader-unique-id="298"><code data-reader-unique-id="299">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="300"><code data-reader-unique-id="301">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="302">print</code><code data-reader-unique-id="303">(comment, replies, end </code><code data-reader-unique-id="304">=</code> <code data-reader-unique-id="305">'\n\n'</code><code data-reader-unique-id="306">)</code></p>

<p data-reader-unique-id="308"><code data-reader-unique-id="309">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="310"><code data-reader-unique-id="311">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="312">replies </code><code data-reader-unique-id="313">=</code> <code data-reader-unique-id="314">[]</code></p>

<p data-reader-unique-id="316"><code data-reader-unique-id="317">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code></p>
<p data-reader-unique-id="318"><code data-reader-unique-id="319">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="320">if</code> <code data-reader-unique-id="321">'nextPageToken'</code> <code data-reader-unique-id="322">in</code> <code data-reader-unique-id="323">video_response:</code></p>
<p data-reader-unique-id="324"><code data-reader-unique-id="325">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="326">video_response </code><code data-reader-unique-id="327">=</code> <code data-reader-unique-id="328">youtube.commentThreads().</code><code data-reader-unique-id="329">list</code><code data-reader-unique-id="330">(</code></p>
<p data-reader-unique-id="331"><code data-reader-unique-id="332">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="333">part </code><code data-reader-unique-id="334">=</code> <code data-reader-unique-id="335">'snippet,replies'</code><code data-reader-unique-id="336">,</code></p>
<p data-reader-unique-id="337"><code data-reader-unique-id="338">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="339">videoId </code><code data-reader-unique-id="340">=</code> <code data-reader-unique-id="341">video_id,</code></p>
<p data-reader-unique-id="342"><code data-reader-unique-id="343">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="344">pageToken </code><code data-reader-unique-id="345">=</code> <code data-reader-unique-id="346">video_response[</code><code data-reader-unique-id="347">'nextPageToken'</code><code data-reader-unique-id="348">]</code></p>
<p data-reader-unique-id="349"><code data-reader-unique-id="350">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="351">).execute()</code></p>
<p data-reader-unique-id="352"><code data-reader-unique-id="353">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="354">else</code><code data-reader-unique-id="355">:</code></p>
<p data-reader-unique-id="356"><code data-reader-unique-id="357">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code data-reader-unique-id="358">break</code></p>


<p data-reader-unique-id="361"><code data-reader-unique-id="362">video_id </code><code data-reader-unique-id="363">=</code> <code data-reader-unique-id="364">"Enter Video ID"</code></p>


<p data-reader-unique-id="367"><code data-reader-unique-id="368">video_comments(video_id)</code></p>
</div>
</td>
</tr>
</tbody>
</table></div>
</div></div>

</div>

</div></div></div></div>
<p data-reader-unique-id="369"><strong data-reader-unique-id="370">Output:</strong></p>
<p data-reader-unique-id="371"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20201221230842/Capture.JPG" data-reader-unique-id="372"></p>
<p data-reader-unique-id="373"><strong data-reader-unique-id="374">Let’s verify the results:</strong></p>
<figure data-reader-unique-id="375"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20201214130339/Screenshot213.png" data-reader-unique-id="376"><p data-reader-unique-id="377" style="font-style: italic;"><strong data-reader-unique-id="378">3 Comments and 2 Replies</strong></p></figure>
<br data-reader-unique-id="379">                                 <div data-reader-unique-id="381"><p data-reader-unique-id="382">Don't miss your chance to ride the wave of the data revolution! Every industry is scaling new heights by tapping into the power of data. Sharpen your skills and become a part of the hottest trend in the 21st century.</p>
<p data-reader-unique-id="383">Dive into the future of technology - explore the <a href="https://www.geeksforgeeks.org/courses/data-science-live?utm_source=geeksforgeeks&amp;utm_medium=article_bottom_text&amp;utm_campaign=courses" data-reader-unique-id="384">Complete Machine Learning and Data Science Program</a> by GeeksforGeeks and stay ahead of the curve.</p></div><br data-reader-unique-id="385">
                                    
                            <div data-reader-unique-id="386">
                                                                    <p data-reader-unique-id="387">
                                        <span data-reader-unique-id="388">Last Updated : </span>
                                        <span data-reader-unique-id="389">03 Aug, 2023</span>
                                    </p>
                                                                
                                 
                            </div>

                            
                            
    <div data-reader-unique-id="405">
        <p data-reader-unique-id="406">
            <span data-reader-unique-id="407">Share your thoughts in the comments</span>
        </p>
        
    </div>                             
                        </div>
