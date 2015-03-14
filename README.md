# AppCacheLoader
**ACLP = Application Cache + Loading Page  Pattern**  

According to [Google's  PageSpeed Rules and Recommendations](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/page-speed-rules-and-recommendations):
"To deliver the fastest time to first render, you want to minimize and (where possible) eliminate the number of critical resources on the page, minimize the number of downloaded critical bytes, and optimize the critical path length.
"  
### This demo achieve these goals:
1. Deliver the loading page as soon as possible, without any external css and javascript,which may **"incur a minimum of two roundtrips before the page can be displayed"** <https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp>

2. Loading other resources to **Html5 Application Cache**, so the follow pages could read data directly from cache.

#### Where to use ***ACLP*** pattern?
* I use it in mobile webapp. [The modern mobile browser support the Application Cache](http://caniuse.com/#feat=offline-apps), the compatiablity is not the problem  

#### How to design the Loading Page?
The *Loading Page*'s function is equal to the splash page in iPhone, give some animation and instruction to distract user's attention on the download speed. Especially for the user first use the webapp, it is a good time give the user a instruction to read. Reading and unstanding the instruction take user's time, make user do not feel the loading progress. The more wonderful thing is , the next time the loading page is not necessary, and user do not want be forced to read instruction again and again. The tech model and user mental model are perfect match.  

#### How to refresh the cache resource?
Modify the appcache.manifest file. For example, the version number.

#### The Alternate Solution 
Async javascript without render-blocking is another solution. 
