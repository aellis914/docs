---
layout: page
weight: 0
title: Parse Settings
navigation:
   show: true
---

{% anchor h2 %}
Get Current Settings 
{% endanchor %}

<table id="parameters-get" class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>get</em>
         </td>
         <td>Retrieve Parse settings</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer must be registered under your account</td>
         <td>The customer who we will update</td>
      </tr>
      <tr>
         <td>method</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>parse</em>
         </td>
         <td>Allows you to access parse functionality</td>
      </tr>
   </tbody>
</table>


{% apiexample get POST https://api.sendgrid.com/apiv2/reseller.manage api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=parse&task=get&method=parse&user=customer@example.com %}
  {% response json %}
{
  "parse": [
    {
      "hostname": "www.example.com",
      "url": "www.mydomain.com/parse.php",
      "spam_check": 1
    }
  ]
}
  {% endresponse %}
  {% response xml %}
<parse>
   <entry>
      <hostname>www.example.com</hostname>
      <url>www.mydomain.com/parse.php</url>
      <spam_check>1</spam_check>
   </entry>
</parse>

  {% endresponse %}
{% endapiexample %}

* * * * *

{% anchor h2 %}
Create New Entry 
{% endanchor %}

<table id="parameters-create" class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>set</em>
         </td>
         <td>Set Parse settings</td>
      </tr>
      <tr>
         <td>hostname</td>
         <td>Yes</td>
         <td>No more than 255 characters</td>
         <td>Hostname we will use with your email</td>
      </tr>
      <tr>
         <td>url</td>
         <td>Yes</td>
         <td/>
         <td>The parse destination</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer must be registered under your account</td>
         <td>The customer who we will update</td>
      </tr>
      <tr>
         <td>method</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>parse</em>
         </td>
         <td>Allows you to access parse functionality</td>
      </tr>
   </tbody>
</table>


{% apiexample create POST https://api.sendgrid.com/apiv2/reseller.manage api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1&method=parse&task=set&method=parse&user=customer@example.com %}
  {% response json %}
{
  "message": "success"
}
  {% endresponse %}
  {% response xml %}
<result>
   <message>success</message>
</result>

  {% endresponse %}
{% endapiexample %}

* * * * *

{% anchor h2 %}
Edit Entry 
{% endanchor %}

<table id="parameters-edit" class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>update</em>
         </td>
         <td>Set Parse settings</td>
      </tr>
      <tr>
         <td>hostname</td>
         <td>Yes</td>
         <td>No more than 255 characters</td>
         <td>Hostname entry you want to update</td>
      </tr>
      <tr>
         <td>url</td>
         <td>Yes</td>
         <td/>
         <td>The parse destination</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer must be registered under your account</td>
         <td>The customer who we will update</td>
      </tr>
      <tr>
         <td>method</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>parse</em>
         </td>
         <td>Allows you to access parse functionality</td>
      </tr>
   </tbody>
</table>


{% apiexample edit POST https://api.sendgrid.com/apiv2/reseller.manage api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1&method=parse&task=update&user=customer@example.com %}
  {% response json %}
{
  "message": "success"
}
  {% endresponse %}
  {% response xml %}
<result>
   <message>success</message>
</result>

  {% endresponse %}
{% endapiexample %}

* * * * *

{% anchor h2 %}
Delete Entry 
{% endanchor %}

<table id="parameters-delete" class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>delete</em>
         </td>
         <td>Set Parse settings</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer must be registered under your account</td>
         <td>The customer who we will update</td>
      </tr>
      <tr>
         <td>hostname</td>
         <td>Yes</td>
         <td>Must be the hostname you wish to delete.</td>
         <td>The host name you will remove for your customer</td>
      </tr>
      <tr>
         <td>method</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>parse</em>
         </td>
         <td>Allows you to access parse functionality</td>
      </tr>
   </tbody>
</table>


{% apiexample delete POST https://api.sendgrid.com/apiv2/reseller.manage api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&task=delete&method=parse&user=customer@example.com %}
  {% response json %}
{
  "message": "success"
}
  {% endresponse %}
  {% response xml %}
<result>
   <message>success</message>
</result>

  {% endresponse %}
{% endapiexample %}