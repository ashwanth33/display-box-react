import React, { useState } from "react";
import "./App.css";

function App() {
  const [showTextbox, setShowTextbox] = useState(false);
  const [textboxValue, setTextboxValue] = useState("");
  const [calculatedValue, setCalculatedValue] = useState(null);

  const handleCheckboxChange = () => {
    setShowTextbox(!showTextbox);
  };

  const handleTextboxChange = (event) => {
    const value = event.target.value;
    setTextboxValue(value);
  };

  return (
    <div className="App">
      <div>
        <input
          type="text"
          value={textboxValue}
          onChange={handleTextboxChange}
          placeholder="Enter a value"
        />
      </div>
      <div>
        <label>
          <input type="checkbox" onChange={handleCheckboxChange} />
           click here to check the double of the value
        </label>
      </div>
      <div>
        {showTextbox && (
          <input
            type="text"
            value={
              2 * Number(textboxValue) == 0 ? "N/A" : 2 * Number(textboxValue)
            }
            onChange={handleTextboxChange}
            placeholder="Enter a value"
          />
        )}
      </div>
    </div>
  );
}

export default App;
