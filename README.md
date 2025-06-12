portfolio-react/
├── public/
│   └── portada.jpg
├── src/
│   ├── components/
│   │   ├── Header.jsx
│   │   ├── Main.jsx
│   │   ├── Estudios.jsx
│   │   ├── SoftSkills.jsx
│   │   └── Footer.jsx
│   ├── pages/
│   │   └── Home.jsx
│   ├── styles/
│   │   └── App.css
│   ├── App.js
│   └── index.js
└── package.json
import React from 'react';
import '../styles/App.css';

const Header = () => {
  return (
    <header className="header">
      <img src="/portada.jpg" alt="Mi foto de portada" className="portada" />
      <h1>Augusto Nicolás Tula</h1>
    </header>
  );
};

export default Header;
import React from 'react';
import Estudios from './Estudios';
import SoftSkills from './SoftSkills';

const Main = () => {
  const proyectos = [
    { nombre: 'App de Tareas', descripcion: 'CRUD con React y Zustand' },
    { nombre: 'Clon de Google', descripcion: 'Búsqueda y diseño con Vite + React Router' },
  ];

  const experiencia = [
    { puesto: 'Soporte Técnico', empresa: 'Freelance', año: '2023' },
  ];

  const idiomas = ['Español (nativo)', 'Inglés (básico escrito)'];

  const certificados = ['Curso de Git y GitHub - Udemy', 'Curso de React Básico - YouTube'];

  return (
    <main>
      <div id="presentacion">
        <p>Soy Augusto Nicolás Tula, estudiante de Programación en la Facultad Regional Tucumán...</p>
      </div>

      <Estudios />
      <SoftSkills />

      <section id="proyectos">
        <h2>Proyectos Realizados</h2>
        <ul>
          {proyectos.map((proy, i) => (
            <li key={i}><strong>{proy.nombre}</strong>: {proy.descripcion}</li>
          ))}
        </ul>
      </section>

      <section id="experiencia">
        <h2>Experiencia Laboral</h2>
        <ul>
          {experiencia.map((exp, i) => (
            <li key={i}>{exp.puesto} - {exp.empresa} ({exp.año})</li>
          ))}
        </ul>
      </section>

      <section id="idiomas">
        <h2>Idiomas</h2>
        <ul>
          {idiomas.map((idioma, i) => (
            <li key={i}>{idioma}</li>
          ))}
        </ul>
      </section>

      <section id="certificados">
        <h2>Certificados</h2>
        <ul>
          {certificados.map((cert, i) => (
            <li key={i}>{cert}</li>
          ))}
        </ul>
      </section>
    </main>
  );
};

export default Main;
import React from 'react';

const Estudios = () => (
  <section id="estudios">
    <h2>Estudios</h2>
    <p>Secundario completo en Colegio Nuestra Señora del Valle.</p>
    <p>Actualmente cursando la Tecnicatura Universitaria en Programación.</p>
  </section>
);

export default Estudios;
import React from 'react';

const SoftSkills = () => {
  const skills = ['Responsabilidad', 'Trabajo en equipo', 'Proactividad', 'Comunicación', 'Adaptabilidad'];

  return (
    <section id="softskills">
      <h2>Soft Skills</h2>
      <ul>
        {skills.map((s, i) => <li key={i}>{s}</li>)}
      </ul>
    </section>
  );
};

export default SoftSkills;
import React from 'react';

const Footer = () => (
  <footer>
    <p>Redes Sociales:</p>
    <a href="https://github.com/totont27" target="_blank" rel="noopener noreferrer">GitHub</a> |{' '}
    <a href="https://www.linkedin.com/in/augusto-nicolas-tula-b32097286/" target="_blank" rel="noopener noreferrer">LinkedIn</a>
  </footer>
);

export default Footer;
import React from 'react';
import Header from '../components/Header';
import Main from '../components/Main';
import Footer from '../components/Footer';

const Home = () => {
  return (
    <>
      <Header />
      <Main />
      <Footer />
    </>
  );
};

export default Home;
// Nombre: Augusto Nicolás Tula
// Legajo: 61574

import React from 'react';
import Home from './pages/Home';
import './styles/App.css';

function App() {
  return <Home />;
}

export default App;
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f7f9fc;
  color: #333;
}

header {
  text-align: center;
  background-color: #282c34;
  color: white;
  padding: 20px;
}

.portada {
  width: 150px;
  border-radius: 50%;
  margin-bottom: 10px;
}

main {
  padding: 20px;
}

section {
  margin-bottom: 20px;
}

footer {
  text-align: center;
  background-color: #282c34;
  color: white;
  padding: 10px;
}
