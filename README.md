nginx 1.21.6, php 8.1.2, postgres 14.2

<hr>

<p>Launch using docker:</p>
<p><code>docker-compose up --build</code></p>
<hr>
<p>So, how I can install new project with composer?</p>
<ol>
Steps to install new composer project
  <li><code>docker-compose up --build</code></li>
  <li>In new terminal run command <code>docker ps</code></li>
  <li>Now u can see containers, find CONTAINER ID of PHP IMAGE (for example 220def7aa3a3)</li>
  <li>Run command to open bash: <code> docker exec -it 220def7aa3a3 bash</code></li>
  <li>Go to projects folder <code>cd /var/www</code></li>
  <li>Because project folder is already used, and composer cannot install new project in existing directory, we will create on new folder. For example, we create a new laravel project. <code>composer create-project laravel/laravel app</code></li>
  <li>Than, we need push this app to our nginx/fpm folder, launch this command to copy all files: <code>cp -R app/* project/</code></li>
  <li>After that u need copy hidden files (.env for example): <code>cp -R app/.[^.]* project/</code></li>
  <li>Add permissions to project, u can try <code>chmod 777 -R project/</code> or find something better.</li>
  <li>After that, u can check <code>localhost</code> in your browser.</li>
</ol>
