# ID-Assignment2
<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://hongyih.github.io/ID-Assignment2/ID-Assignment2(final)%20(final)/main/index.html">
    <img src= "./assets/pokemonlogo.png" alt="PokePng" width = "auto" height="80">
  </a>

  <h3 align="center">My Pokemon API Website</h3>

  <p align="center">
    This is a website that makes use of PokeApi to retrieve information for personal use. For example, to find out more information on  specific pokemon that exists as of when this website was made.
    <br />
    <a href="https://github.com/HongYih/ID-Assignment2"><strong>Explore the docs »</strong></a>
    <br />
    <br />
  </p>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">Table of Contents</h2></summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contacts</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

Hi, my name is Lee Hong Yih from class IT03. This repository contains all the information I used to make this project with. This README will be a comprehensive guide to how this was done and I hope the information given is sufficient for your understanding!
### Built With

* Visual Studio Code
* GitHub
* GetBootStrap


<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these simple steps:

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/HongYih/ID-Assignment2.git
   ```
2. Install NPM packages
   ```sh
   npm install
   ```



<!-- USAGE EXAMPLES -->
## Usage
### Techniques
```javascript
const fetchPokemon = () => {
    const promises = [];
    for (let i = 1; i <= 150; i++) {
        const url = `https://pokeapi.co/api/v2/pokemon/${i}`;
        promises.push(fetch(url).then((res) => res.json()));
    }
    Promise.all(promises).then((results) => {
        const pokemon = results.map((result) => ({
            name: result.name,
            image: result.sprites['front_default'],
            type: result.types.map((type) => type.type.name).join(', '),
            id: result.id
        }));
        displayPokemon(pokemon);
    });
};
```
1. Retrieving the information from PokeApi using __Promises__
  * we only get one shot at mutating each promise
  * we need to make sure to write `.catch`
  * and we need to map them with `.map`
  

```javascript
const fetchPokemon = async () => {
    const url = `https://pokeapi.co/api/v2/pokemon?offset=386&limit=108`;
    const res = await fetch(url);
    const data = await res.json();
    const pokemon = data.results.map((data, index) => ({
        name: data.name,
        id: index + 387,
        image: `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${index + 387}.png`
    }));

    displayPokemon(pokemon);
};
```
2. Using __async-wait__
   * `async` functions return a promise
   * `await` blocks the execution of the code within the `async` function in which it is located
   * cleaner code

```javascript
$.ajax({
      url: url,
      dataType: "json",
      method: "GET",
```
3. Using __ajax__
   * `ajax` helps to retrieve information from an API and allows the retriever to make use of the retrieved information
   * easy to read and map data


<!-- ROADMAP -->
## Roadmap
### My Commits
<img src= "./README_assets/commits.PNG" alt="My Commits" width = "auto" height="auto">

1. Commit 1
  * starting my website mainframe
2. Commit 2
  * starting to build source code for javascript
3. Commit 3
  * building and working on the javascript for fetching pokemon
4. Commit 4
  * solving pokemon type errors for javascript and adding abilities
5. Commit 5
  * fixing html, css and javascript build errors
6. Commit 6
  * solidifying js, html and css and also adding icons
  * fixing issues with the js not working sometimes (bug fixes)
7. Commit 7
  * trying out and working on the pop-up function
8. Commit 8
  * adding regions to it and finalising it
9. Commit 9
  * finishing touches and final touchups
<!-- CONTACT -->
## Contact

Email - s10185009@connect.np.edu.sg

Project Link: [https://hongyih.github.io/ID-Assignment2/ID-Assignment2(final)%20(final)/main/index.html](https://hongyih.github.io/ID-Assignment2/ID-Assignment2(final)%20(final)/main/index.html)



<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements

* PokeAPI (https://pokeapi.co/)
* Research (https://medium.com/@sergio13prez/fetching-them-all-poke-api-62ca580981a2
)
* Inspiration (https://codepen.io/jamesqquick/pen/NWKaNQz)
* Video Idea (https://www.youtube.com/watch?v=tFVdxGgJPCo)





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
