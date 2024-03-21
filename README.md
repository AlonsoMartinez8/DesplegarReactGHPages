# Desplegar React GHPages
Tutorial para **desplegar** una App de *React* usando *GitHub Pages* en **5 pasos**.
### Requisitos
- Node **→** npm
- Git
- GitHub
### Contenido
1. Crear repositorio GitHub
2. Crear App React
3. Configurar App
4. Desplegar
5. Configurar GitHub Pages
## 1. Crear repositorio GitHub
En nuestra cuenta de Git Hub crearemos un **nuevo repositorio**:
1. Click en Nuevo Repositorio
2. Proporcionar nombre y descripción(opcional) al repositorio
3. Visibilidad pública
4. Click en crear
## 2. Crear App React
En nuestra terminal ejecutamos:
```bash
npx create-react-app nombre-app
```
Tras ello, instalamos GHPages:
```bash
npm install gh-pages --save-dev
```
## 3. Configurar App
En el archivo ***package.json***:
1. Añadir propiedad *homepage*.
```json
{
  ...
  "homepage": "https://{nombreUsuarioGitHub}.github.io/{nombreRepositorio}",
  ...
}
```
2. Añadir **scripts** para desplegar.
```json
"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d build",
  ...
```
## 4. Desplegar
Antes de desplegar es necesario inicializar el **repositorio Git** del proyecto y conectar con el repositorio remoto de GitHub:
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/{nombreUsuarioGitHub}/{nombreRepositorio}.git
git push -u origin main
```
A continuación, para desplegar en el repositorio GitHub ejecutamos:
```bash
npm run deploy -- -m "Deploy React app to GitHub Pages"
```
## 5. Configurar GitHub Pages
1. En GitHub, navegar hacia los **ajustes** de *GitHub Pages*
2. Configurar "Build and Deployment"
	- **Source**: Deploy from a branch
	- **Branch**:
	  -   Branch:  `gh-pages`
      -   Folder:  `/ (root)`
 3. Click en guardar.
