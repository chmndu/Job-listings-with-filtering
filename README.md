# Frontend Mentor - Job listings with filtering solution

This is a solution to the [Job listings with filtering challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/job-listings-with-filtering-ivstIPCt). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size
- See hover states for all interactive elements on the page
- Filter job listings based on the categories

### Screenshot

![](./screenshot.jpeg)

### Links

- Solution URL: [Solution URL here](https://www.frontendmentor.io/solutions/responsive-job-listings-with-filtering-using-react-js-4lfy-9FjIb)
- Live Site URL: [Live site URL here](https://job-listings-with-filtering-eight-xi.vercel.app/)

## My process

### Built with

- Flexbox
- Mobile-first workflow
- [React](https://reactjs.org/) - JS library


### What I learned

In this project, I learned to use below code snippets:

```js
// Function to handle clicks on filter tags
function handleClick(event){
    const filteredTag = event.target.textContent; // Get the clicked tag's text
    if(!filterTags.includes(filteredTag)){ // If tag is not already in the filter list
        setFilterTags(f => [...f, filteredTag]); // Add tag to the filterTags array
        setShowFilter(true); // Show the filter component
    }
}

// Function to remove a specific filter tag by its index
function removeFilterTag(index){
    setFilterTags(filterTags.filter((_, i) => i !== index)); // Remove the tag at the given index
    if(filterTags.length === 1){ // If only one tag remains, hide the filter component
        setShowFilter(false);
    }
}
```
```jsx
{/* Render filtered job listings if a filter is applied */}
{showFilter && jobs.filter(value =>
    filterTags.every(tag =>
        value.role.includes(tag) ||
        value.level.includes(tag) ||
        value.languages.includes(tag) ||
        value.tools.includes(tag)
    )
).map((job, index) => (
    <Job key={index} {...job} newJob={job.new} onClick={handleClick}/>
))}
```

### Continued development

I'm looking to improve my CSS & JavaScript knowledge to design more unique and new stuff.

## Author

- Frontend Mentor - [@chmndu](https://www.frontendmentor.io/profile/chmndu)
- LinkedIn - [Chamindu Dahanayaka](https://www.linkedin.com/in/chamindudahanayaka/)