# React

## Javascript library used to run application on browsers rather than rendering in server side. The application is develop via components

---

## Links

* [Academind](https://academind.com/community/)
* [React documentation](https://reactjs.org/)

we can run react without cmd-line by using codepen.io

Introduction to first REACT APP in codepen:
* import the cdn of react and react-dom into the js settings section
* choose Babel as the javascript pre-processor to run the application
	Note: Babel is a opensource transcompiler(converting the latest-edge javascript,ES6 to plain-older version of javascript which is compatible with the javascript engines)
* Ran code of root/demo.html

## Why should we choose react ?

1) helps with problem of managing the states of UI elements, -> UI STATE MANAGEMENT is way better
2) focuses on business logic, not on app from exploding
3) It is maintained by a huge community which means the code will be in highly optimized format , hence bigger the application better will be the performance

## Alternatives

* Angular
* Vue
* Backbone/ amber

## Understanding SPA and MPA

1) SINGLE PAGE APPLICATIONS:
	*we will get only one page from the server(that is whenever a user visits the website), content is rendered on client
	* we will have a root react component followed by the any number of child components
	* Thus from the above mentioned point we can say cleary that there will be only one reactdom to render in the web page

2) MULTI PAGE APPLICATIONS:
	*we will get multiple pages from the server that is server decides where the user has to be sent, thus content rendenring done at server
	* this is widely used to create widgets, that individual components are dumped in to specific part of web page and changing respective component
	* we will have multiple plain html pages with some components of react
	* thus from the above point we can clearly say that we call the reactdom render() to build respective components UI, there fore we may need to render multiple times

Next: [Next-Gen Javascript](./02-Next%20Gen%20Javascript.md)
