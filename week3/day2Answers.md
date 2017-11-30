// What is the difference between HashRouter and BrowserRouter?

    //HashRouter is a little easier because the server looks at only what is before the #. React will look at the rest?

    //With BrowserRouter it will look at the whole url and if you haven't configured your server to handle that it will break all the things. 



// How do you import HashRouter?

    //import { HashRouter } from 'react-router-dom';
    //import { HashRouter as router } from 'react-router-dom'; //gives it an alias so you can just reference it as router.
    
    //You can only do one HashRouter tag per component.
    
    
    
// What do you need to import to set up routes within your HashRouter?

    //To use routes must import import { HashRouter, Route } from 'react-router-dom';
    //Routes have to be inside of the HashRouter tags in your render. 



// How would you set up your render to have two routes one to home and one to about using HashRouter?


    // <HashRouter>
    //     <div>
    //         <Route exact path='/' component={Home}>
    //         <Route path='/about' component{About}>
    //     </div>
    // </HashRouter>
    
    //Use exact on your path for whichever one is your default path '/' so it only brings in the home component and not also the about component. Basically just keep exact with / so it doesn't break all the things because nested routes will get broken.
    


// How do you import Link to use it with your routes you've created so you don't have to type in the url?
    
    //import { HashRouter, Route, Link } from 'react-router-dom';
    
    
// What does Link tags to and give an example of two link tags?

    //Link tags are like your href it changes your path in the url. 
    //Links us to the url endings and when it matching our path the route will render our component.

    //<Link to='/'>Home</Link>
    //<Link to='/about'>About</Link>


//**NavLink: Allows you to have activeClassName which makes life way easier for UI. You can import it like Link from 'react-router-dom'.
    
    
    
// What does Switch do?

    // Makes it so you only load one route at a time.

    //You can nest routes into your switch tag. Switch makes it so that it will only load one page at a time. The first one that matches that path is the one that will load and it won't load anything else. Loads one route at a time. It will look at your routes in order so /about/:faq will need to be above /about. 



// How do you import Switch so that you can use it in your React app?

    //import { HashRouter, Route, Link, Switch } from 'react-router-dom';
    
    
    
// Give an example of Switch syntax?

    //    <Switch>
    //     <Route exact path='/' component={Home}>
    //       <Route exact path='/about/:faq' component={Faq}>
    //     <Route exact path='/about' component={About}>
    //    </Switch>
    
    
    
// If you need to pass and id as a parameter to your url how would you set that up in your route and your link tags?

    //<Route exact path='/product/:id' component={product}>
    //<Link to={'/product/' + id }>About</Link>
    
    
// How do you access the id off a parameter in your url?

    //this.props.match.params.id


// How would you create nested links within a route? 

    // <Route path='/about' render={() => {
    //       return (
    //         <About>
    //             <Switch>
    //                 <Route path='/about/history' component={ History } />
    //                 <Route path='/about/contact' component={ Contact } />
    //             </Switch>
    //         </About>

    //     )
    //     }}/>
    
    
    
// How do you display the nested routes on your component?

    //{ this.props.children } 
    
    // Any time you don't use a self closing component tag <About /> but use <About></About> Anything that goes in between those two tags will be the children of that component and can be access by using this.props.children. 
    
    // the render is loading a component that isn't self closing. Inside of the two tags for the component, there is a switch with routes. The props.children represents what goes between the two tags for the component.
    

//**Example of Index.js file: 

// import React from 'react';
// import ReactDOM from 'react-dom';
// import { HashRouter } from 'react-router-dom';
// import './index.css';
// import App from './App';

// ReactDOM.render(
//     <HashRouter>
//       <App />
//     </HashRouter>
// , document.getElementById('root'));

  
    
    
//**Example of a router.js file: 

// import React from 'react';
// import { Route, Switch } from 'react-router-dom';
// import Home from './components/Home/Home';
// import About from './components/About/About';
// import History from './components/History/History';
// import Contact from './components/Contact/Contact';
// import ClassList from './components/ClassList/ClassList';
// import Student from './components/Student/Student';

// export default (
//     <Switch>
//         <Route exact path='/' component={ Home }/>
//         <Route path='/about' render={() => {
//           return (
//             <About>
//                 <Switch>
//                     <Route path='/about/history' component={ History } />
//                     <Route path='/about/contact' component={ Contact } />
//                 </Switch>
//             </About>

//         )
//         }}/>
//         <Route path='/classlist' component={ ClassList } />
//         <Route path='/student/:id' component={ Student } />
//     </Switch>
// )


//**Example of App.js file: 

// import React, { Component } from 'react';
// import { Link } from 'react-router-dom';
// import router from './router';
// import './App.css';

// export default class App extends Component {


//     render() {
//         return (
//           <div className=''>
//               <nav className='nav'>
//                   <div>WestSide University</div> 
//                   <div className='link-wrap'>
//                         <Link to="/" className='links'>Home</Link>
//                         <Link to="/about" className='links'>About</Link> 
//                   </div>  
//               </nav>
//             { router }
//           </div> 
//         )
//     }


// }