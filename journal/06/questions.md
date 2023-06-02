# Single Page Applications with Vue
01. What is the entrypoint of an application?

  > | The router holds all the paths within an application. All the doors. To access the application, the path is built into the router and the door can then be opened. |

02. What is the difference between a vue `component` and `page`?

  > | Pages are more of a single use component within the mvc framework. Components are specific groups of code that can be used in multiple places within the program.  |

03. What is ***Component-Based Architecture***?

  > | it's a concept introduced by React.js. it encapsulates components, which are individual pieces of a larger interface, into smaller independent micro systems. Each of these components can act on their own accord within the page, refresh individually, have their own interfaces, and make their own calls to the server. They're not reliant on the page as a whole to refresh or talk to the server to act.   |

04. What are the three tags that make up a Vue component?

  > | Template (the layout of the page), Script (the javascript functions for the component to act), and the Style(the css for designing the look of the components and page) |

05. What are ***lifecycle hooks***? What are lifecycle hooks used for?

  > | Lifecycle Hooks let you look into the api or server behind the scenes and see what's happening. They let you know when a component is created, it's added to the DOM, or updated/destroyed. They have creation hooks(which run first before the DOM loads), mounting hooks(these work on page load for the items you want to appear when the page first renders), updating hooks(when the page calls to the server or needs to refresh), and destruction hooks(i don't quite understand these ones or when they're used. it talks about the component being destroyed so that makes me think they use it in delete buttons.) |

06. Which component in Vue does the vue-router use to mount pages onto?

  > | router-link. After the page is mounted in the router, attaching this allows the redirection from one page to the next.  |

07. What is the difference between the `AppState` and the state object within a component?

  > | The AppState is the global brains of the application. The state object within a component is an object that can be shared within the application. |

08. What is the responsibility of `Services` in our Vue projects?

  > | The services contain all the functions pertaining to their specific titled service. They hold the params, the data they reference, and their functions. They're then imported into the different components to be used as needed. |

09. What are ***props*** and how are they used? Provide an example

  > | props are like highways that pass information between components but only passed down. it's built out in the component, then you can just add <Xxxx/> in the template for the html to link the entire object.  |

10. What is the Vue method used to create watchable objects such as `state` or `AppState`?

  > | I'm not too sure. I can't remember if it's one of the hooks that's used or somehthing different, but my brain is too fried to find it.  |
