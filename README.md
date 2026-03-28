import React, { useEffect, useRef } from "react";
import gsap from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

export default function App() {
  const heroRef = useRef(null);

  useEffect(() => {
    const ctx = gsap.context(() => {
      gsap.from(".headline span", {
        y: 50,
        opacity: 0,
        stagger: 0.05,
        duration: 0.8,
        ease: "power2.out",
      });

      gsap.from(".stat", {
        y: 20,
        opacity: 0,
        stagger: 0.2,
        delay: 0.5,
      });

      gsap.fromTo(
        ".car",
        {
          x: -300
        },
        {
          x: window.innerWidth,
          scale: 1.05,
          ease: "none",
          scrollTrigger: {
            trigger: heroRef.current,
            start: "top top",
            end: "+=1000",
            scrub: 1,
            pin: true
          },
        }
      );
    }, heroRef);

    return () => ctx.revert();
  }, []);

  const text = "WELCOME ITZ FIZZ";

  return (
    <div className="bg-black text-white min-h-[200vh]">
      <section
        ref={heroRef}
        className="h-screen flex flex-col items-center justify-center relative overflow-hidden"
      >
        <h1 className="headline text-4xl md:text-6xl tracking-[0.5em] mb-8">
          {text.split("").map((char, index) => (
            <span key={index} className="inline-block">
              {char}
            </span>
          ))}
        </h1>

        <div className="flex gap-8 text-center">
          <div className="stat">
            <h2 className="text-2xl font-bold">120%</h2>
            <p>Growth</p>
          </div>
          <div className="stat">
            <h2 className="text-2xl font-bold">80%</h2>
            <p>Users</p>
          </div>
          <div className="stat">
            <h2 className="text-2xl font-bold">95%</h2>
            <p>Satisfaction</p>
          </div>
        </div>

        <img
          src="https://images.unsplash.com/photo-1503376780353-7e6692767b70"
          alt="car"
          className="car absolute bottom-10 left-0 w-64 md:w-96"
        />
      </section>

      <section className="h-screen flex items-center justify-center">
        <h2 className="text-3xl">Scroll to see animation</h2>
      </section>
    </div>
  );
}
