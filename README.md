Download Link: https://assignmentchef.com/product/solved-ece4830-lab3
<br>
Lets start with the following filter:

Find the differential equation for the input<em> x</em>(<em>t</em>) and output <em>y</em>(<em>t</em>) relationship of the voltages.

Express it in discrete time by substituting for example <em><sup>dy</sup></em><sup>(<em>t</em>)</sup> for <em><sup>y</sup></em><sup>[<em>n</em>]</sup><sup></sup><em><sup>y</sup></em><sup>[<em>n</em></sup><sup></sup><sup>1] </sup>where<em> T<sub>s</sub></em> will be

<em>dt                   T<sub>s</sub></em>

the sample period.

Calculate its <em>z</em> transform and solve for <em>H</em>[<em>z</em>] = <em>Y</em>[<em>z</em>]/<em>X</em>[<em>z</em>]. Use R = 1000 Ω and C = 0.01 μF, and <em>fs</em> = 40 000 Hz.

By using the help command in Matlab, familiarize with the command <em>freqz</em> Plot its frequency response using the following:

[h,w]=freqz(b,a);

plot(40000*w/(2*pi),abs(h))

Your parameters <em>a </em>and <em>b </em> in the command above come from your derivation of <em>H</em>[<em>z</em>].

In general, in order to obtain the impulse response of a system, we would set up an experiment in the lab where we would generate an impulse and measure the response of the system. This is not feasible in most cases. Think of <em>δ</em>(<em>t</em>) in the frequency domain. Would noise be a good choice as a testing signal?

Use the following type of noise X = normrnd(0,1,512,30);

That is 30 realizations of 512 Gaussian distributed samples. Instead of building an RC circuit, we will let Matlab compute the output as

y = filter(b,a,X);

You will be using 30 examples. Average them and see if you obtain a similar result as before. What if you use more than 30 examples, is the result better?

Another choice of testing signal is the chirp, given that name because its “resemblance” to the sound of some birds <em>x</em>(<em>t</em>) = sin(2π<em>f</em><sub>0</sub>(<em>t</em> + <em>Kt</em><sup>2</sup>)), where<em> f</em><sub>0</sub> is the initial frequency and <em>K </em>is a real constant.

For these type of signals the concept of Instantaneous Frequency <em>IF </em>is very helpful:

1 <em>d</em>

<em>IF </em> (<em>t</em>), where <em>x</em>(<em>t</em>)  sin(<em>t</em>)

2 <em>dt</em>

Sample a chirp (<em>t</em> = n<em>T<sub>s</sub></em>)  and use the same amount of samples <em>N</em> for n = 0,2, …, <em>N</em>-1 as before in order to compare it with the noise input example. Choose the parameters <em>f</em><sub>0 </sub>and <em>K</em> as to obtain the best identification of your system. Look at the chirp in the frequency domain first and experiment with different values, although you can derive these values theoretically from the expression of the chirp, <em>IF</em>.

You can identify the system using the commands iddata and arx. Use the command help in Matlab and familiarize with these commands. Use the chirp you created and use it as an input to obtain the output using the results you obtained from the difference equation you found that described the system. Afterwards, these two system identification commands should give you similar parameters of the difference equation coefficients that you calculated theoretically. Think of how useful it is to have input and output signals from a circuit you have no idea what it is and that you can describe the system as easily as this. But, there is always a but, you do need the parameters <em>M</em> and <em>N</em> and if you do not know the order of the model you may end up with identifying a system that can give you trouble.

Problems

5.3.4 5.3.6       5.3.7    5.4.3 part (a)

<table>

 <tbody>

  <tr>

   <td width="96"></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

5.4.10 5.5.4     5.6.5    5.8.14


