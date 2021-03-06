# Pi
**Wikipedia Definition of the mathematical constant:**
http://en.wikipedia.org/wiki/Pi

**π  vs pi (The real number and the nearest double precision number)**


Most of the time, 
it is not worth making a large distinction between the real mathematical constant π (which can not  be represented exactly in double
precision on a computer) and the 64 bit double precision number pi.
However, since functions like sine are ill-conditoned at multiples of
π, and high school teachers drill into us identities such as sin(π)=0.
a certain emotional concern shows up when we see sin(pi) being merely
small and not 0.  Sometimes this feels perhaps unnecessarily like a disconcerting experimental error.  See 
<a href="https://github.com/alanedelman/JuliaNumerics/blob/master/Functions/Elementary%20Functions/Sine.md">
(The sine page) </a> for further discussion on the distinction between
sin(π) and sin(pi).


<table>
<tr>
<td>
π
</td>
<td>
</td>
<td>
 3.14159265358979323846264338328
</td>
</tr>
<tr>
<td>
pi
</td>
<td>
 2^1*(1+2570638124657944/2^52)
</td>
<td>
 3.14159265358979311599796346854
</td>
</tr>
</table>


(See the modpi function)
