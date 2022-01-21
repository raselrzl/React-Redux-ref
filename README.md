"# React-Redux-ref" 

export default class App extends Component {

  state ={
    name:'Ryu',
    age: 30
  }
  handleChange=(e)=>{
    this.setState({
      name:e.target.value
    });
  }

  render() {
    return (
      <div className="app-content">
        
        <h1>My name is: {this.state.name} and I am {this.state.age}</h1>
        <form>
          <input type="text" onChange={this.handleChange}></input>
          <button>Submit</button>
        </form>

        
      </div>
    )
  }
---------------------------------------------------------------------------------


import './App.css';

import React, { Component } from 'react'
import PropTypes from 'prop-types'

export default class App extends Component {

  state ={
    name:'Ryu',
    age: 30
  }
  handleChange=(e)=>{
    this.setState({
      name:e.target.value
    });
  }
  handleSubmit=(e)=>{
    e.preventDefault();
    console.log('Form submitted', this.state.name)
     
    
  }
  render() {
    return (
      <div className="app-content">
        
        <h1>My name is: {this.state.name} and I am {this.state.age}</h1>
        <form onSubmit={this.handleSubmit}>
          <input type="text" onChange={this.handleChange}></input>
          <button>Submit</button>
        </form>

        
      </div>
    )
  }
}



---------------------------------------------------------------------------

import React, { Component } from 'react'

class Zeras extends Component {

    render() {
        const {name, age, belt}=this.props;

        console.log(this.props)
        return (
            <div className='ras'>
            <div>Name: {name}</div>
            <div>Age: {age}</div>
            <div>Belt: {belt}</div>
                
            </div>
        )
    }
}
export default Zeras;
-------------------------------------------------------------------------

import React from 'react'

const Zeras= ({zerass})=>{
        /* const zerasList=zerass.map(zeras=>{
            if(zeras.age>20){

            return(
            <div className='ras' key={zeras.id}>
                <div>Name: {zeras.name}</div>
                <div>Age: {zeras.age}</div>
                <div>Belt: {zeras.belt}</div>                
            </div>
            )
            }else{
                return null
            }
        }) */
         
        const zerasList=zerass.map(zeras=>{
            return zeras.age>20 ? (
                <div className='ras' key={zeras.id}>
                <div>Name: {zeras.name}</div>
                <div>Age: {zeras.age}</div>
                <div>Belt: {zeras.belt}</div>                
            </div>    
            ) : null;
        })



       // console.log(this.props)
        return (
            <div className='zeras-list'>
                { zerasList }
            </div>
            
        )
    }
export default Zeras;
---------------------------------------------------------------
import React, { Component } from 'react'


class AddZeras extends Component {

    state={
        name:null,
        age:null,
        belt: null
    }
    handleChange =(e)=>{
        this.setState({
            [e.target.id]:e.target.value
        })
    }


    handleSubmit=(e)=>{
        e.preventDefault();
        console.log(this.state);
    }



    render() {
        return (
            <div>
                <form onSubmit={this.handleSubmit}>
                    <label htmlFor="name">Name:</label>
                    <input type="text" id="name" onChange={this.handleChange} />

                    <label htmlFor="name">Age:</label>
                    <input type="text" id="age" onChange={this.handleChange} />

                    <label htmlFor="name">Belt:</label>
                    <input type="text" id="belt" onChange={this.handleChange}/>

                    <button>Submit</button>

                </form>
            </div>
        )
    }
}
export default AddZeras
------------------------------------------------------------------------------------------

