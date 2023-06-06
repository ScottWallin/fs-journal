# Managing the Fullstack Application

1. Describe the two ways to bind Data in Vue?

  > | The first way uses {{}}. This allows the data to come in and be filled in as the reference pulls it to change the HTML. The other way is with v-bind. this uses v-bind then :x  to bind the attributes that are needed within the tag so whatever the tag wraps around will update within the HTML. |

2. The `SPA` acronym stands for what?

  > | Single Page Application. This allows vue to reload parts of the page without reloading the entire page. Makes for better connectivity within the application and for the user to have a better experience. Deals with building the back side and the front side to utilize api's and their communication. |

3. What are some of the advantages/uses of a `SPA` over a traditional one?

  > | Better connectivity within the application. Allows a more seamless user experience. Allows parts of the application to reload without needing the entire page to reload at once. |

4. What does the `onMounted` method in Vue do?

  > | onMounted allows the functions described underneath to come in on page load.  |

5. What is the `v-model` attribute in Vue for, and when might you use it?

  > | v-model is part of what's used for binding components to the page. When a component is called <X />, v-model goes within that tag to emit an event when the component is called.  |

6. What is the package.json file used for?

  > | this holds all of the metadata for a project to be used or read. it also contains the functional metadata to be called on.  |

7. Which Vue attributes(directives) could you use to conditionally render elements on a page?

  > | v-if (an if statement), v-else (an else statement), v-else-if (an else-if statement) |

8. What is the purpose of the `key` attribute when using `v-for` on an element?

  > | the key attribute allows vue to to use the key as a roadmap to find a node's identity and reuse it without having to reorder the DOM. It's best to use a :key when using v-for.|

9. What is the `<slot>` element and what is it used for?

  > | these are used to pass html to a parent element from child element. let's us reuse modals or other elements as needed and to slot in specific pieces. |
