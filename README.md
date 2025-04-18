// ...existing imports
import { Phone, Mail } from "lucide-react";
import { useEffect } from "react";

// ...rest of code

// Inside your component function, before the return statement
useEffect(() => {
  const script = document.createElement("script");
  script.src = "https://cdn.jsdelivr.net/npm/@chatscope/chat-ui-kit-styles@latest/dist/default/styles.min.css";
  script.async = true;
  document.head.appendChild(script);

  const css = document.createElement("link");
  css.rel = "stylesheet";
  css.href = "https://cdn.jsdelivr.net/npm/@chatscope/chat-ui-kit-styles@latest/dist/default/styles.min.css";
  document.head.appendChild(css);
}, []);

// Insert this at the beginning of the component return, for 3D animation section
<div className="relative bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 h-screen flex flex-col justify-center items-center px-4">
  {/* 3D Product Card */}
  <div className="group perspective-1000">
    <div className="w-64 h-96 bg-white rounded-xl shadow-lg transform transition-transform duration-500 group-hover:rotate-y-180">
      <div className="w-full h-full flex flex-col justify-center items-center p-6 transform-style preserve-3d">
        <h1 className="text-2xl font-bold text-gray-800 mb-4">Featured Product 🎉</h1>
        <p className="text-lg text-gray-600">Experience the 3D twist in shopping!</p>
      </div>
    </div>
  </div>

  {/* Shop Now Button with 3D effect */}
  <div className="mt-8">
    <button className="bg-yellow-500 text-white py-2 px-6 rounded-full text-xl transform transition-transform duration-300 hover:-translate-y-1 hover:shadow-xl">
      Shop Now 🛍️
    </button>
  </div>
</div>

<style jsx>{`
  .perspective-1000 {
    perspective: 1000px;
  }
  .preserve-3d {
    transform-style: preserve-3d;
  }
  .group:hover .group-hover\:rotate-y-180 {
    transform: rotateY(180deg);
  }
  .group-hover\:rotate-y-180 {
    transform: rotateY(0deg);
    transition: transform 0.5s;
  }
`}</style>

// Insert this at the end of the component return, just before closing </div>

{/* Customer Service Section */}
<div id="support" className="mt-20 px-4 max-w-3xl mx-auto text-left">
  <h2 className="text-2xl font-bold text-fuchsia-700 mb-2">Customer Service 📞</h2>
  <p className="text-lg text-gray-700 mb-2">
    Need help with your order or have any questions? Our friendly support team is here to help!
  </p>
  <div className="bg-white p-4 rounded-xl shadow space-y-2">
    <div className="flex items-center gap-2">
      <Phone className="text-fuchsia-600" />
      <span className="text-md">+1 (800) 123-4567</span>
    </div>
    <div className="flex items-center gap-2">
      <Mail className="text-fuchsia-600" />
      <span className="text-md">support@funzone.com</span>
    </div>
    <p className="text-sm text-gray-500 mt-2">
      Support available Mon-Fri, 9am to 6pm (EST)
    </p>
  </div>
</div>

{/* Live Chat Widget (AI-Powered Simulation) */}
<div className="fixed bottom-4 right-4 z-50 w-80 max-w-full">
  <div className="bg-white rounded-xl shadow-lg overflow-hidden border border-fuchsia-300">
    <div className="bg-fuchsia-600 text-white p-3 font-bold text-center">💬 Chat with FunBot</div>
    <div className="p-3 text-sm text-gray-700 h-48 overflow-y-auto">
      <p><strong>FunBot:</strong> Hi there! 👋 How can I help you today?</p>
      <p className="mt-2"><em>(This is a mock AI assistant. Real-time response not yet active.)</em></p>
    </div>
    <div className="flex p-2 border-t">
      <input type="text" placeholder="Type your message..." className="flex-1 border rounded-lg p-2 text-sm" disabled />
      <button className="ml-2 px-3 bg-fuchsia-500 text-white rounded-lg text-sm" disabled>Send</button>
    </div>
  </div>
</div>

// ...closing </div> of main container

