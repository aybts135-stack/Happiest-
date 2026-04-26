# Happiest 20th Birthday 
.card {
  position: relative;
  width: 300px;
  height: 400px;
  perspective: 1200px; /* Essential for 3D depth */
  cursor: pointer;
}

.outside {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  transition: transform 1s;
  transform-style: preserve-3d;
  z-index: 2;
  transform-origin: left; /* Card opens from the left side */
}

.card:hover .outside {
  transform: rotateY(-130deg); /* Reveals the inside on hover */
}

.front, .back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  border-radius: 15px;
}

.front {
  background: rgba(142, 68, 173, 0.8); /* Purple tint */
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: 2px solid white;
}

.back {
  background: #2c003e; /* The "back side" of the front cover */
  transform: rotateY(180deg);
}

.inside {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border-radius: 15px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  z-index: 1;
}
