<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.date | date: "%B" }} {{ post.date | date: "%d" | plus:'0' }}, {{ post.date | date: "%Y" }} - {{ post.title }}</a>
    </li>
  {% endfor %}
</ul>



### Older Posts

I wrote a number of articles at Wordpress - https://andrewwhitten.wordpress.com/ . Some that may be of interest are:

- Things to know about Permissions before starting Salesforce Functions - <a href="https://andrewwhitten.wordpress.com/2021/11/25/things-to-know-about-permissions-before-starting-salesforce-functions/">LINK</a>
- Salesforce LWC inheritance and code sharing - <a href="https://andrewwhitten.wordpress.com/2021/05/12/salesforce-lwc-inheritance-and-code-sharing/">LINK</A>
- Data Quality Analysis in Salesforce files with MuleSoft Anypoint - <a href="https://andrewwhitten.wordpress.com/2021/02/13/analyze-files-in-salesforce-with-mulesoft-anypoint/">LINK</A>
- Creating a Salesforce Permission Set subset from multiple Profiles - <a href="https://andrewwhitten.wordpress.com/2020/12/29/creating-a-salesforce-permission-set-subset-from-multiple-profiles/">LINK</a>

