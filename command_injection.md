<a href=README.md><img align="left" height="50" src="https://user-images.githubusercontent.com/35313265/127749412-a8b42cd6-0285-449e-97b8-4f9e46b57dce.png" title="main page"></a>
<a href="sql_injection.md"><img align="right" height="50" src="https://user-images.githubusercontent.com/35313265/127749414-2252b86a-76dd-4a42-8acf-4c3d88667f2f.png" title="SQL Injection"></a>

# Command Injection

## 📝Description accoding to **OWASP** (*Open Web Application Security Project*):

<b>Command injection</b> is an attack in which the goal is execution of arbitrary commands on the host operating system via a vulnerable application. Command injection attacks are possible when an application passes unsafe user supplied data (forms, cookies, HTTP headers etc.) to a system shell. In this attack, the attacker-supplied operating system commands are usually executed with the privileges of the vulnerable application. Command injection attacks are possible largely due to insufficient input validation.<br/><br/>

This attack differs from Code Injection, in that code injection allows the attacker to add their own code that is then executed by the application. In Command Injection, the attacker extends the default functionality of the application, which execute system commands, without the necessity of injecting code.
<hr/>

## 💡Solution accoding to [**RailsGuides**](https://guides.rubyonrails.org/v2.3.11/security.html):

If your application has to execute commands in the underlying operating system, there are several methods in Ruby: **exec(command)**, **syscall(command)**, **system(command)** and **\command**. You will have to be especially careful with these functions if the user may enter the whole command, or a part of it. This is because in most shells, you can execute another command at the end of the first one, concatenating them with a semicolon (;) or a vertical bar (|).<br/><br/>

A countermeasure is to use the 👉**system(command, parameters)** method which passes command line parameters safely.
```ruby
# prints "hello; rm *" and does not delete files
system("/bin/echo","hello; rm *")
```
<hr/>
<p><a href=README.md><img align="left" height="50" src="https://user-images.githubusercontent.com/35313265/127749412-a8b42cd6-0285-449e-97b8-4f9e46b57dce.png" title="main page"></a>
<a href="sql_injection.md"><img align="right" height="50" src="https://user-images.githubusercontent.com/35313265/127749414-2252b86a-76dd-4a42-8acf-4c3d88667f2f.png" title="SQL Injection"></a></p>
