import React, { useState, useEffect } from 'react';

function App() {
  const [data, setData] = useState([]);

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => setData(data));
  }, []);

  return (
    <div className="container mx-auto p-4">
      <h1 className="text-3xl font-bold">Data</h1>
      <ul>
        {data.map(item => (
          <li key={item.id} className="py-2">
            {item.name}
          </li>
        ))}
      </ul>
    </div>
  );
}

export default App;
