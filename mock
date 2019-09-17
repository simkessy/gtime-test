/*
Your task is to use an API to render a list of “tiles” on a screen. Since Gametime is focused on mobile, the UI you will build looks very similar to a mobile app irrespective of if you are writing this in React or React Native. Please see the attached video for an example of what your solution should look like, and an example of the API response.

https://www.dropbox.com/s/pk85psroipj4r8x/client-phone-screen-mobile.MOV?dl=0

https://gist.githubusercontent.com/mattbanach/0fe32399c26cb4d2faf7453fafd3ea18/raw/f5064cca7b60cc7ff5c8f3d1b00b3345f1f076a6/tiles.json

For the purpose of this exercise, we’ll write everything out in one plain text file. Use comments to delineate where you would have different files. Use any resources you’d like, and keep in mind that the purpose of the exercise is to see your approach to the problem— we’ll never actually run your code. 

A few quick notes:
- Just start writing components. You do not need to worry about scaffolding. 
- Feel free to use online resources-- if you’d use it at your job, you can use it here. 
- CoderPad will not run your solution. The goal is to see how you break the problem apart and devise your solution. Yes, it may feel uncomfortable writing code without an IDE-- don’t stress about getting single detail right.
- Please vocalize your thought process as you move through the challenge. Ask as many questions as you need!

*/

// need to pull data using - api: https://gist.githubusercontent.com/mattbanach/0fe32399c26cb4d2faf7453fafd3ea18/raw/f5064cca7b60cc7ff5c8f3d1b00b3345f1f076a6/tiles.json

// Resources:
// {
//     "response": [
//         {
//             "title": "A Lake!",
//             "subtitle": "Glacier National Park?",
//             "id": "a",
//             "imageURL": "https://www.desktop-background.com/p/2011/04/26/194095_interfacelift-1280x800-tablet-wallpapers-sorted-by-downloads_1920x1408_h.jpg"
//         }
//     ]
// }


// src
    // api
        // matts_api
        // index.js
    // components 
        // Cards.js
        // App.js 
 // index.js

// api/matts_api.js
export const getResources = async() => {
    let data = await fetch("https://gist.githubusercontent.com/mattbanach/0fe32399c26cb4d2faf7453fafd3ea18/raw/f5064cca7b60cc7ff5c8f3d1b00b3345f1f076a6/tiles.json")
    
    return await data.getJSON();
}

// api/index.js
import {getResources} from './matts_api';
export {getResources};


// Card.js
import React from 'react'

export default function Card() {
    const {title, subtitle, id, imageURL} = props.resource
    
    return (
        <div id={`card-${id}`} className={`card-container`}>
            <img src={imageUrl} className={`card-image`}>
            <h3 className={`card-title`}>{title}</h3>
            <p className={`card-subtitle`}>{subtitle}</p>
        </div>
    )
};

// App.js
import React, { Component, Fragement } from 'react'
import { Matts_API } from "./api/"
import { Card } from "./components/Cards"
export default class App extends Component {
    constructor() {
        this.state = {
            resources: []
        }
    }
    
    
    // Doucle check sync on async life methods
    async componentDidMount () {
        // Make call to rest endpoint
        let data = await getResources()
        // Once you get resources, update state 
        this.setState({...this.state, resources: data.response})
    }
    
    render() {
        return (
            <Fragement>
                {
                    this.state.resources.map( resource => {
                        return <Card key={resource.id} resource={resource} /> 
                    })
                }
            <Fragement/>
        )
    }
}


// index.js 
import React from "react";
import { render } from "react-dom";
import { App } from "./components/App";

render(<App />, document.getElementById("root"));
