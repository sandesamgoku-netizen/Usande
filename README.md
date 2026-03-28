<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Curso de Inglês Online</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>Curso de Inglês Online</h1>
    <nav>
      <a href="#home">Início</a>
      <a href="#videos">Vídeo Aulas</a>
      <a href="#contato">Contato</a>
    </nav>
  </header>

  <section id="home">
    <h2>Bem-vindo!</h2>
    <p>Aprenda inglês de forma prática e divertida com nossas vídeo aulas.</p>
  </section>

  <section id="videos">
    <h2>Vídeo Aulas</h2>
    <!-- Exemplo com vídeo do YouTube -->
    <div class="video-container">
      <iframe width="560" height="315" 
        src="https://www.youtube.com/embed/VIDEO_ID" 
        title="Video aula de inglês" 
        frameborder="0" allowfullscreen>
      </iframe>
    </div>

    <!-- Exemplo com vídeo local -->
    <video width="560" controls>
      <source src="videoaula.mp4" type="video/mp4">
      Seu navegador não suporta vídeo.
    </video>
  </section>

  <section id="contato">
    <h2>Contato</h2>
    <form>
      <label for="nome">Nome:</label>
      <input type="text" id="nome" name="nome" required>
      
      <label for="email">Email:</label>
      <input type="email" id="email" name="email" required>
      
      <textarea placeholder="Sua mensagem"></textarea>
      <button type="submit">Enviar</button>
    </form>
  </section>

  <footer>
    <p>&copy; 2026 Curso de Inglês Online</p>
  </footer>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  background: #f4f4f4;
}

header {
  background: #0044cc;
  color: white;
  padding: 15px;
  text-align: center;
}

nav a {
  color: white;
  margin: 0 10px;
  text-decoration: none;
}

section {
  padding: 20px;
  background: white;
  margin: 20px;
  border-radius: 8px;
}

.video-container {
  margin-bottom: 20px;
}

form {
  display: flex;
  flex-direction: column;
}

form input, form textarea {
  margin: 10px 0;
  padding: 8px;
}

button {
  background: #0044cc;
  color: white;
  border: none;
  padding: 10px;
  cursor: pointer;
}
    
