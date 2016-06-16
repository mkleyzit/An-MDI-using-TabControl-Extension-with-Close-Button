# An MDI using TabControl Extension with Close Button
![Screenshot](http://www.stresstimulus.com/image/mdi.png)
<h2>Introduction</h2>
I work on a team developing a .NET WinForm application. In the new version, 
we needed to add a Multi Document Interface (MDI). The requirement was that 
users should be able to easily open and close multiple tabs attached to various 
documents.<br><br>
Unfortunately, Microsoft TabControl does not support a close button on 
individual tabs. I found several neat controls made from scratch with the close 
button. However, after implementing them in our application, we started getting 
sporadic crashes with <code>AccessViolationException</code>.<br><br>
A possible reason for this is that our application spans hundreds of threads. 
It is a load testing tool which emulates multiple web users and measures website 
performance under load in order to test its scalability. Also, the documents 
handle large reports with rich content (graphs, dynamic images, grids, browser 
controls, etc.), or large WinForms. So, I needed a very scalable, yet simple 
solution that works under heavy load on OS. I didn’t need any fancy woodwork; I 
just needed to draw a close button while maintaining bulletproof reliability. So 
instead of developing another tab control from scratch, I extended the standard <code>TabControl </code>and 
set the <code>DrawMode </code>to <code>OwnerDrawFixed</code>.<br><br>
<h2>Features</h2>
<ul>
	<li>A tab control extends the <code>System.Windows.Forms.TabControl </code>class.	</li>
	<li>The tab page control that extends the <code>System.Windows.Forms.TabPage </code>class.
	</li>
	<li>The tab pages have an optional close button for MDI support. </li>
	<li>Selected tab has bold text. </li>
	<li>Highlights unselected tab when mouse hovers over. </li>
	<li>Comes with a standard close button image and close button hover image, 
	both of which are customizable. </li>
	<li>Added a tab close event which is raised when a tab is closed. </li>
</ul>
