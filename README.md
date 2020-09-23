<div align="center">

## Quick tip on how to handle NULL in ADO\.net


</div>

### Description

If you're an old ADO programmer, you may be frustrated by not knowing exactly how to check for NULL. Here's a 1 second tip on how to do it in ADO.NET.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Ian Ippolito \(vWorker\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/ian-ippolito-vworker.md)
**Level**          |Beginner
**User Rating**    |4.9 (151 globes from 31 users)
**Compatibility**  |VB\.NET, ASP\.NET
**Category**       |[Databases](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/databases__10-5.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/ian-ippolito-vworker-quick-tip-on-how-to-handle-null-in-ado-net__10-141/archive/master.zip)





### Source Code


<p>If you try the old fashioned way of checking for null:</p>
<p>&nbsp;&nbsp;&nbsp; If IsNull(rsCompany(&quot;Name&quot;)) Then</p>
<p>Visual Studio will tell you that IsNull is not supported and to use DBNull
instead.&nbsp; At first I thought this was really nice.&nbsp; However, when I
tried to do:</p>
<p>&nbsp;&nbsp;&nbsp; If rscompany(&quot;Name&quot;) = DBNull Then</p>
<p>I got an error about assignments not allowed to a type!&nbsp; What was I to
do?</p>
<p>The Visual Studio help was its usual cryptic self (&quot;The DBNull class is for
handling NULL values&quot;...accurate by not alot of help).&nbsp; After some fumbling
around, I stumbled on the answer, and thought I'd share it to hopefully save
someone 5 minutes of having to research it:<br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp; If rsCompany(&quot;Name&quot;) is DBNull.Value then</p>
<p>Hope this saves you some time!</p>
<p>&nbsp;</p>

