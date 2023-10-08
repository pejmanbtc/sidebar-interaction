# sidebar-interaction

## Simple conversion codes for dark and light screen

import React, { useState } from 'react';

const App = () => {
  const [isOverlayVisible, setOverlayVisible] = useState(false);

  const darkenScreen = () => {
    setOverlayVisible(true);
  };

  const lightenScreen = () => {
    setOverlayVisible(false);
  };

  return (
    <div className="flex items-center justify-center min-h-screen">
      {isOverlayVisible && (
        <div className="fixed top-0 left-0 w-full h-full bg-black bg-opacity-50 z-50"></div>
      )}
      <div className="relative z-50">
        <h1 className="text-2xl font-bold mb-4">Website Content</h1>
        <p>This is the main content of the website.</p>
        <button
          className="bg-white border border-gray-300 text-black px-4 py-2 text-center text-sm rounded-md m-2 cursor-pointer"
          onClick={darkenScreen}
        >
          Darken Screen
        </button>
        <button
          className="bg-white border border-gray-300 text-black px-4 py-2 text-center text-sm rounded-md m-2 cursor-pointer"
          onClick={lightenScreen}
        >
          Lighten Screen
        </button>
      </div>
    </div>
  );
};

export default App;
