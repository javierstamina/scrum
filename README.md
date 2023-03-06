### Hola 👋, estos son algunos certificados sobre SCRUM que voy adquiriendo.
<p>
<a href="https://twitter.com/Javier_Argo" target="_blank">
   <img align="left" alt="twitter" src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white" />
</a>&nbsp;&nbsp;

<a href="https://discordapp.com/users/JavierArgo#5553" target="_blank">
   <img align="left" alt="discord" src="https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white" />
</a>&nbsp;&nbsp;

<a href="https://www.linkedin.com/in/javierargo/" target="_blank">
   <img align="left" alt="linkedin" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
</a>
<p/>

<br/>

<div class="grid">
  <?php
  $files = glob('*.*');
  foreach($files as $file) {
    $ext = pathinfo($file, PATHINFO_EXTENSION);
    if ($ext != 'md') { // Excluye el archivo README.md
      echo '<div class="item"><a href="['.$file.'](https://github.com/javierstamina/scrum/blob/master/SPFC%20Certiprof%202023.pdf)" target="_blank"><img src="['.$file.'](https://github.com/javierstamina/scrum/blob/master/SPFC%20Certiprof%202023.pdf)" alt="'.$file.'"></a></div>';
    }
  }
  ?>
</div>

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  grid-auto-rows: 200px;
  gap: 10px;
}

.item {
  position: relative;
  overflow: hidden;
}

.item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s;
}

.item:hover img {
  transform: scale(1.1);
}

.item::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  opacity: 0;
  transition: opacity 0.3s;
}

.item:hover::after {
  opacity: 1;
}

.item a {
  display: block;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
}


const items = document.querySelectorAll('.item');
items.forEach(item => {
  item.addEventListener('click', () => {
    const fileUrl = item.querySelector('a').href;
    window.open(fileUrl, '_blank');
  });
});

