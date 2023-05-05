Download Link: https://assignmentchef.com/product/solved-ece-4122-6122-hmk-6
<br>
<strong><u>Notes:</u></strong>

You can write, debug and test your code locally on your personal computer.  <u>However, the code you</u> <u>submit must compile and run correctly on the PACE-ICE server</u>.

<strong><u>Submitting the Assignment:</u></strong>

See Appendix C.

<h1>Grading Rubric</h1>

<strong>AUTOMATIC GRADING POINT DEDUCTIONS : </strong>

<table width="619">

 <tbody>

  <tr>

   <td width="154"><strong>Element </strong></td>

   <td width="192"><strong>Percentage Deduction </strong></td>

   <td width="272"><strong>Details </strong></td>

  </tr>

  <tr>

   <td width="154">Does Not Compile</td>

   <td width="192">40%</td>

   <td width="272">Code does not compile on PACE-ICE!</td>

  </tr>

  <tr>

   <td width="154">Chessboard</td>

   <td width="192">8% (up to)</td>

   <td width="272">Board drawn incorrectly</td>

  </tr>

  <tr>

   <td width="154">Chess pieces</td>

   <td width="192">32% (up to)</td>

   <td width="272">-1 for each piece drawn incorrectly (size and/or location)</td>

  </tr>

  <tr>

   <td width="154">Initial lighting/material</td>

   <td width="192">10% (up to)</td>

   <td width="272">5 for each light not working correctly(includes turning on and off)</td>

  </tr>

  <tr>

   <td width="154">Enable features are working</td>

   <td width="192">10% (up to)</td>

   <td width="272">Double buffering, depth, smooth modeling, etc…</td>

  </tr>

  <tr>

   <td width="154">Key press actions</td>

   <td width="192">30% (up to)</td>

   <td width="272">Divided equally among key presses excluding turning lights on/off.</td>

  </tr>

  <tr>

   <td width="154">Clear Self-Documenting Coding Styles</td>

   <td width="192">10% (up to)</td>

   <td width="272">This can include incorrect indentation, using unclear variable names, unclear/missing comments, or compiling with warnings. (See Appendix A)</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong>LATE POLICY </strong>

<table width="619">

 <tbody>

  <tr>

   <td width="154"><strong>Element </strong></td>

   <td width="102"><strong>Percentage Deduction </strong></td>

   <td width="363"><strong>Details </strong></td>

  </tr>

  <tr>

   <td width="154">Late Deduction Function</td>

   <td width="102">score –(20/24)*H</td>

   <td width="363"> H = number of hours (ceiling function) passed deadline  note : Sat/Sun count as one day; therefore H = 0.5*H<sub>weekend</sub></td>

  </tr>

 </tbody>

</table>

<strong><u>OpenGL Chess Set</u></strong>




You need to create a 3D chess set model using OpenGL following these rules:




<ol>

 <li>Create a chessboard which is a 8 x 8 grid of alternating light and dark squares in the xy plane, as seen below, with each square being 1 m x 1 m. The origin of your model is at the lower left-hand corner.  The positive z-axis is up out of the page</li>

</ol>




<ol start="2">

 <li>There are 6 types of chess pieces which are to be represent by 6 different GLUT shapes</li>

</ol>




<ol>

 <li>pawn shall be represented using a glutSolidSphere</li>

 <li>rook shall be represented using a glutSolidCube</li>

 <li>knight shall be represented using a glutSolidTeapot</li>

 <li>bishop shall be represented using a glutSolidCone</li>

 <li>queen shall be represented using a glutSolidTetrahedron</li>

 <li>king shall be represented using a glutSolidOctahedron</li>

</ol>




<ol start="3">

 <li>Each piece (light and dark) shall be placed in the correct starting location as shown in the figure for part 1.</li>

 <li>Each piece shall be sized and/or scaled so that it has a bounding box of 0.75 m width,</li>

</ol>

0.75 m depth, and 1.0 m height.

<ol start="5">

 <li>Each piece needs to be centered in the correct square and sitting flush with the surface of the chessboard</li>

 <li>The light colored pieces should have a RGB color of RGB (140, 140, 135).</li>

 <li>The dark colored pieces should have a RGB color of RGB (150, 75, 0).</li>

 <li>Enable ambient lighting (GL_LIGHT0) and one diffuse light (GL_LIGHT1). GL_LIGHT1 located at (5, 5, 8)

  <ol>

   <li>GLfloat light0_ambient[] = { 0.2, 0.2, 0.2, 1.0 };</li>

   <li>GLfloat light1_diffuse[] = { 0.5, 0.5, 0.5, 1.0 };</li>

   <li>GLfloat light1_specular[] = { 0.3, 0.3, 0.3, 1.0 };</li>

  </ol></li>

</ol>




<ol start="9">

 <li>Setup the following material properties for the pieces</li>

</ol>

GLfloat mat_specular[] = { 0.5, 0.5, 0.5, 1.0 };     GLfloat mat_shininess[] = { 50.0 };




<ol start="10">

 <li>Enable depth testing.</li>

 <li>Use a smooth shading model.</li>

 <li>The viewport (window size) shall be width of 600 and height of 600.</li>

 <li>The viewport can be resized and the view of the chess set remain correct.</li>

 <li>Use double buffering.</li>

 <li>Use a perspective viewing volume, with the eye located at (4, -5, 10) with a large enough field-of-view to see the whole chess set. The viewing volume should be centered on the center of the chessboard (4, 4, 0).</li>

 <li>Key press commands (the center of the view volume is always maintained at (4, 4, 0)

  <ol>

   <li>Pressing ‘r’ or ‘R’ key rotates the chess set by 10 degrees around the z-axis at its center point each time.</li>

   <li>Pressing ‘d’ or ‘D’ key moves the eye location down z –axis 0.25 m each time.</li>

   <li>Pressing ‘u’ or ‘U’ key moves the eye location up z-axis 0.25 m each time.</li>

   <li>Pressing ‘0’ (zero) key toggles GL_LIGHT0 on and off (enable/disable)</li>

   <li>Pressing ‘1’ key toggles GL_LIGHT1 on and off (enable/disable)</li>

   <li><strong><u>ECE6122 students</u></strong> also do the extra following additional commands.

    <ol>

     <li>Presses a ‘k’ or “K” causing a random knight to move only one position forward or one position backwards, assuming the move is allowed. If the move is not allowed then a new random knight is chosen until one can move. The piece can disappear and reappear.</li>

     <li>Presses a ‘p’ or “P” causing a random pawn to move one position forward or backwards the correct amount, assuming the move is allowed. If the move is not allowed then a new random pawn is chosen until one can move.  The piece can disappear and reappear.</li>

    </ol></li>

  </ol></li>

</ol>

<strong> </strong>

<strong> </strong>

<strong>Extra Credit: </strong>

Pressing the ‘E’ or ‘e’ key toggles between normal mode and enhanced mode that makes some of the pieces look more realistic (discretion of TAs if it is good enough)

<ul>

 <li>Pawn (+1), Rook (+1), Bishop (+1)</li>

 <li>Knight (+4), King (+2), Queen (+2)</li>

</ul>













<strong><u>Appendix A: Coding Standards</u></strong> <strong> </strong>

<em><u>Indentation</u></em>:

When using <em>if/for/while</em> statements, make sure you indent 4 spaces for the content inside those.  Also make sure that you use spaces to make the code more readable.

For example:

for (int i; i &lt; 10; i++)

{     j = j + i;

}




If you have nested statements, you should use multiple indentions. Each { should be on its own line (like the <em>for</em> loop) If you have <em>else</em> or <em>else if</em> statements after your <em>if</em> statement, they should be on their own line.

for (int i; i &lt; 10; i++)

{

if (i &lt; 5)    {        counter++;         k -= i;     }           else

{                            k +=1;    }         j += i;

}




<em><u>Camel Case:</u> </em>

This naming convention has the first letter of the variable be lower case, and the first letter in each new word be capitalized (e.g. firstSecondThird). This applies for functions and member functions as well! The main exception to this is class names, where the first letter should also be capitalized.

<em><u>Variable and Function Names</u>:</em>

Your variable and function names should be clear about what that variable or function is. Do not use one letter variables, but use abbreviations when it is appropriate (for example: “imag” instead of

“imaginary”). The more descriptive your variable and function names are, the more readable your code will be.  This is the idea behind self-documenting code.

<em>                 </em>

<em><u>File Headers</u>: </em>

Every file should have the following header at the top

/*

Author: &lt;your name&gt;

Class: ECE4122 or ECE6122

Last Date Modified: &lt;date&gt;




Description:




What is the purpose of this file?




*/

<em><u>Code Comments:</u> </em>




<ol>

 <li>Every function must have a comment section describing the purpose of the function, the input and output parameters, the return value (if any).</li>

 <li>Every class must have a comment section to describe the purpose of the class.</li>

 <li>Comments need to be placed inside of functions/loops to assist in the understanding of the flow of the code.</li>

</ol>







<strong> </strong>




<strong><u>Appendix B: Submitting Assignment</u></strong>

<u>Step-By-Step Submitting a Tar.gz</u>

<strong><em><u>PLEASE NOTE:</u></em></strong> All the following instructions are run on PACE. If you are struggling with any of the steps, please come see the TAs during office hours. Better to start and test early than wait until the last minute.

Below is a step-by-step tutorial on how to create the .tgz file for Homework 6 for ECE 4122/6122.

Additionally, if you do not use a header file for a solution, you do not need to submit a header file. Please adjust these instructions accordingly. The tarball should contain a folder with your buzzid containing a subfolder for the problem with the corresponding .cpp and .h files.

Please make sure that the problem is in a subfolder with the naming conventions:   &lt;FirstName_LastName&gt;_Hmk6




Create a subdirectory named <em>buzzid </em>in the current working directory by executing the following command in the shell:

$ mkdir <em>buzzed </em>

Create a text file named <strong>manifest.</strong>




Please make sure that the <strong>manifest</strong> file is a plain text file and not a rich text file. Microsoft word will generate a rich text file. The easiest method to create a plain text file is to use a command line editor such as vi, vim, or nano.

(If you want a tutorial, these can be useful: vi:

<a href="http://heather.cs.ucdavis.edu/%7Ematloff/UnixAndC/Editors/ViIntro.html">http://heather.cs.ucdavis.edu/~matloff/UnixAndC/Editors/ViIntro.html</a><a href="http://heather.cs.ucdavis.edu/%7Ematloff/UnixAndC/Editors/ViIntro.html">,</a> vim: <a href="https://openvim.com/">https://openvim.com/</a><a href="https://openvim.com/">,</a> nano: <a href="https://www.howtogeek.com/howto/42980/the-beginners-guide-to-nano-the-linux-command-line-text-editor/">https://www.howtogeek.com/howto/42980/the-beginners-guide-to-nano-the-linux-command</a><a href="https://www.howtogeek.com/howto/42980/the-beginners-guide-to-nano-the-linux-command-line-text-editor/">line-text-editor/</a><a href="https://www.howtogeek.com/howto/42980/the-beginners-guide-to-nano-the-linux-command-line-text-editor/">)</a>

Populate the <strong>manifest</strong> file with the following:




<em>buzzid</em>/&lt;FirstName_LastName&gt;_Hmk6/*.cpp

<em>buzzid</em>/&lt;FirstName_LastName&gt;_Hmk6/*.h







(<strong><em><u>PLEASE NOTE</u></em></strong>: this is subject to change with depending on your class section. The wildcard (*) character will grab all the .cpp and .h files you generated for each problem.)




Now you need to construct the correct file structure for the submission. This means that you need to put all the homework files into your <em>buzzid </em>folder. Execute the following lines in the shell:




$ cp -a &lt;FirstName_LastName&gt;_* <em>buzzid  </em>

<em> </em>

Many people have had issue with this step. You need to make sure the naming conventions are consistent to avoid potential problems.




It is now time to tarball your submission. If all the other steps have gone smoothly execute the following command:




$ tar -zcvf <em>buzzid</em>-hmk6.tgz $(cat manifest)




You can now check the new tgz file just generated with the following command:




$ tar -ztvf <em>buzzid</em>-hmk6.tgz








