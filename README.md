# React - Project

### Installation vite

```bash
npm create vite@latest . -- --template react
```

### Installation react

```bash
npm npm i
```

## Start project

```bash
npm run dev
```

## add components Header Hero Delivery Details Product Application Question Footer
we have also folder constants were we have export all images

## next step we import section from index html to our components
- change class to className
- change way for images
- remember single tag must be have / 
- add all components in App jsx 
- remove App.css

## next step burger menu
- add useState
- change way for icon in css

```bash
const [isActive, setActive] = useState(false)

  const handleToggle = () => {
    setActive(!isActive)
}

```

```bash
 <nav className={isActive ? "nav active": "nav"}>

<div className={isActive ? "burger active": "burger"} onClick={handleToggle}></div>
```

## Next step activate button to top 
- add component ScrollToTop
- add useEffect and useState
- npm i react-icons
- add icon MdKeyboardDoubleArrowUp from https://react-icons.github.io/react-icons/ 
- add function goToTop
- import to App jsx

```bash
const [showTopBtn, setShowTopBtn] = useState(false);

const goToTop = () => {
    window.scrollTo({
        top: 0,
        behavior: 'smooth',
    });
};
```
## Add useEffect
```bash
useEffect(() => {
    window.addEventListener('scroll', () => {
        window.scrollY > 400 ? setShowTopBtn(true) : setShowTopBtn(false);
        // alternative way
        // if(window.scrollY > 400) {
        //   setShowTopBtn(true);
        // } else {
        //   setShowTopBtn(false);
        // }
    });
}, []);

<>
    {showTopBtn &&
        <MdKeyboardDoubleArrowUp className="btn-up" onClick={goToTop} />
    }
</>

```

## Scroll to the section by clicking
- add function scrollToSection  
- change name in menu and add id

```bash
  const scrollToSection = (sectionId) => {
    document.getElementById(sectionId).scrollIntoView({ behavior: 'smooth' });
  };
```
## Activate our product tabs
- add array name button
- create productsList js 
- component Card jsx
- ul change to div
- used useState
- function handleFilter
- used motion library 
https://www.framer.com/motion/introduction/
npm install framer-motion

## 
```bash
["ICE CREAM", "CAYENNE CHOCOLATE", "CAKE BATTER", "CANDY CANE", "PLATTERS", "DESSERT"]
```

```bash
const [filterItems, setFilterItems] = useState(productsList)
const [isActive, setActive] = useState("ICE CREAM");

const handleFilter = category =>{
    setActive(category)
    // console.log(category);
    if (category === "ICE CREAM") {
        setFilterItems(data)
    } else {
        const filterItems = data.filter(item => item.category === category)
        setFilterItems(filterItems)
    }
}
```
## Name category must be uppercase like Array buttons ICE CREAM => ICE CREAM !Important 
```bash
import images from "./constants/data"

const productsList = [
    {
        id:1,
        title: 'Cayenne chocolate',
        text: 'Bon Au Pain is a pioneer in the healthy fast food scene.Bon Au Pain is a pioneer in the healthy fast food scene.Bon Au Pain is a pioneer in the healthy fast food scene',
        price: '$19.55',
        oldPrice: '$22.55',
        img: images.broun,
        category: 'CAKE BATTER',
    },
    {
        id:2,
        title: 'Brown bread',
        text: 'Bon Au Pain is a pioneer in the healthy fast food scene.Bon Au Pain is a pioneer in the healthy fast food scene.Bon Au Pain is a pioneer in the healthy fast food scene',
        price: '$19.55',
        oldPrice: '$22.55',
        img: images.mango,
        category: 'CAYENNE CHOCOLATE',
    },
    {
        id:3,
        title: 'Sweet corn',
        text: 'Bon Au Pain is a pioneer in the healthy fast food scene.Bon Au Pain is a pioneer in the healthy fast food scene.Bon Au Pain is a pioneer in the healthy fast food scene',
        price: '$19.55',
        oldPrice: '$22.55',
        img: images.sweet,
        category: 'CANDY CANE',
    },
    {
        id:4,
        title: 'Sweet corn',
        text: 'Bon Au Pain is a pioneer in the healthy fast food scene.Bon Au Pain is a pioneer in the healthy fast food scene.Bon Au Pain is a pioneer in the healthy fast food scene',
        price: '$19.55',
        oldPrice: '$22.55',
        img: images.mix,
        category: 'PLATTERS',
    },
    {
        id:5,
        title: 'Sweet corn',
        text: 'Bon Au Pain is a pioneer in the healthy fast food scene.Bon Au Pain is a pioneer in the healthy fast food scene.Bon Au Pain is a pioneer in the healthy fast food scene',
        price: '$19.55',
        oldPrice: '$22.55',
        img: images.sweet,
        category: 'DESSERT',
    }
]

export default productsList
```

## Add motion Product

```bash
import {motion, AnimatePresence} from "framer-motion"

```
## Add motion Card 
```bash
import { motion } from 'framer-motion'

initial={{ y: 10, opacity: 0 }}
animate={{ y: 0, opacity: 1 }}
exit={{ y: -10, opacity: 0 }}
transition={{ duration: 0.4 }}
```

## Deploy  project
- https://app.netlify.com/
- add new repo on GitHub
- import project to netlify 
- connection with git repo 

[Like and subscribe video]()  