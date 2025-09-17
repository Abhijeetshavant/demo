"use client";
import React, { useState, useMemo } from "react";

const page = () => {
  const [number, setNumber] = useState(0);
  const [counter, setCounter] = useState(0);

  function cubeNum(num) {
    console.log("Calculation done!");
    return Math.pow(num, 3);
  }
  const result = useMemo(() => cubeNum(number), [number]);
  return (
    <>
      <input
        type="number"
        value={number}
        onChange={(e) => {
          setNumber(e.target.value);
        }}
      />
      <h1>Cube of this number:{result}</h1>
      <button
        onClick={() => {
          setCounter(counter + 1);
        }}
      >
        Counter
      </button>
      <h1>Counter:{counter}</h1>
    </>
  );
};

export default page;




#useContext Hook 
useContext is a React Hook that allows you access data from any component without explicitly passing it down through props at every level
=> useContext is used to manage Global data in the react app
=>src/Context/App.Context.jsx import { createContext } from "react";

export const AppContext = createContext();

const ContextProvider = (props) => {
  const phone = "+1 123456789";
  const name = "Abhijeet";
  return (
    <AppContext.Provider value={{ phone, name }}>
      {props.children}
    </AppContext.Provider>
  );
};
export default ContextProvider;

=>src/Context/
