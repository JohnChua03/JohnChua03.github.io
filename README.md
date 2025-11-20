import { useEffect, useRef } from "react";
import { motion, useScroll, useTransform } from "framer-motion";

// === John Chua — Animated Portfolio (React + Tailwind + Framer Motion) ===
// Notes:
// - This is a single React component you can drop into a Vite/Next/CRA app.
// - Tailwind is assumed (the preview here includes it). If not, you can swap classes for plain CSS.
// - Animations: subtle entrance on scroll, parallax hero, hover lift on cards.

export default function PortfolioSite() {
  const heroRef = useRef(null);
  const { scrollYProgress } = useScroll({ target: heroRef, offset: ["start start", "end start"] });
  const y = useTransform(scrollYProgress, [0, 1], [0, -80]);
  const opacity = useTransform(scrollYProgress, [0, 1], [1, 0.75]);

  const sections = [
    { id: "projects", label: "Projects" },
    { id: "about", label: "About" },
    { id: "contact", label: "Contact" },
  ];

  const projectCards = [
    {
      tag: "Python • DSP",
      title: "Automatic Music Transcriber",
      body: "Real-time note detection using FFT; streams audio and maps to musical notes.",
      link: "#",
    },
    {
      tag: "MATLAB/Simulink • Haptics",
      title: "Teleoperation (Quanser Omni)",
      body: "Leader–follower joint-space control with trajectory record/replay and PID tuning.",
      link: "#",
    },
    {
      tag: "STM32 • Power",
      title: "DC–DC Buck Controller",
      body: "PWM-based regulation; ripple measurement and efficiency characterization across loads.",
      link: "#",
    },
  ];

  return (
    <div className="min-h-screen bg-gradient-to-b from-slate-950 via-slate-900 to-slate-950 text-slate-100">
      <Header sections={sections} />

      {/* HERO */}
      <section ref={heroRef} id="home" className="relative overflow-hidden">
        {/* Blurry gradient blobs */}
        <motion.div
          aria-hidden
          className="pointer-events-none absolute -top-24 -left-16 h-72 w-72 rounded-full bg-fuchsia-500/20 blur-3xl"
          animate={{ y: [0, 16, -8, 0], scale: [1, 1.05, 1], rotate: [0, 8, -6, 0] }}
          transition={{ duration: 10, repeat: Infinity, ease: "easeInOut" }}
        />
        <motion.div
          aria-hidden
          className="pointer-events-none absolute -bottom-24 -right-16 h-80 w-80 rounded-full bg-sky-500/20 blur-3xl"
          animate={{ y: [0, -20, 10, 0], scale: [1, 1.08, 1], rotate: [0, -10, 6, 0] }}
          transition={{ duration: 12, repeat: Infinity, ease: "easeInOut" }}
        />

        <div className="mx-auto grid max-w-6xl grid-cols-1 gap-10 px-5 pb-20 pt-28 md:grid-cols-2 md:gap-12">
          <motion.div style={{ y, opacity }} className="flex flex-col justify-center">
            <h1 className="text-4xl font-extrabold tracking-tight sm:text-5xl">
              John Chua
            </h1>
            <p className="mt-3 max-w-xl text-lg text-slate-300">
              Electrical Engineering student focused on <span className="font-semibold text-sky-300">embedded systems</span> &
              <span className="font-semibold text-fuchsia-300"> power electronics</span>. I build real-time control projects and practical hardware–software systems.
            </p>
            <div className="mt-5 flex flex-wrap gap-2">
              {"Python C C++ STM32 MATLAB/Simulink PSpice".split(" ").map((s) => (
                <span key={s} className="rounded-full border border-slate-700/60 bg-slate-800/60 px-3 py-1 text-sm text-slate-300">
                  {s}
                </span>
              ))}
            </div>
            <div className="mt-6 flex flex-wrap gap-3">
              <a href="#projects" className="rounded-xl bg-sky-500 px-4 py-2 font-semibold text-slate-950 shadow-md shadow-sky-500/30 transition hover:translate-y-[-2px] hover:bg-sky-400">
                See Projects
              </a>
              <a href="mailto:jchua100103@gmail.com" className="rounded-xl border border-slate-700 bg-slate-900 px-4 py-2 font-semibold text-slate-100 transition hover:translate-y-[-2px] hover:border-slate-600">
                Email Me
              </a>
            </div>
          </motion.div>

          <motion.div
            initial={{ opacity: 0, y: 20 }}
            whileInView={{ opacity: 1, y: 0 }}
            viewport={{ once: true, amount: 0.4 }}
            transition={{ duration: 0.6 }}
            className="relative"
          >
            <div className="rounded-3xl border border-slate-800 bg-slate-900/60 p-6 shadow-2xl shadow-black/30 ring-1 ring-white/5">
              <div className="grid grid-cols-3 gap-3">
                {Array.from({ length: 9 }).map((_, i) => (
                  <motion.div
                    key={i}
                    className="aspect-square rounded-2xl bg-gradient-to-br from-slate-800 to-slate-700"
                    whileHover={{ scale: 1.03 }}
                    transition={{ type: "spring", stiffness: 240, damping: 18 }}
                  />
                ))}
              </div>
              <p className="mt-4 text-sm text-slate-400">Aesthetic placeholder — replace with screenshots or a short project collage.</p>
            </div>
          </motion.div>
        </div>
      </section>

      {/* PROJECTS */}
      <section id="projects" className="mx-auto max-w-6xl px-5 py-10">
        <div className="mb-6 flex items-end justify-between">
          <h2 className="text-2xl font-bold">Projects</h2>
          <a href="#" className="text-sm font-semibold text-slate-300 underline-offset-4 hover:underline">
            View all on GitHub
          </a>
        </div>

        <div className="grid grid-cols-1 gap-6 md:grid-cols-3">
          {projectCards.map((p, idx) => (
            <motion.article
              key={p.title}
              initial={{ opacity: 0, y: 18 }}
              whileInView={{ opacity: 1, y: 0 }}
              viewport={{ once: true, amount: 0.3 }}
              transition={{ duration: 0.5, delay: idx * 0.06 }}
              className="group flex h-full flex-col rounded-2xl border border-slate-800 bg-slate-900/60 p-5 shadow-lg shadow-black/20"
            >
              <span className="text-xs uppercase tracking-wide text-slate-400">{p.tag}</span>
              <h3 className="mt-1 text-lg font-semibold">{p.title}</h3>
              <p className="mt-1 text-sm text-slate-300/90">{p.body}</p>
              <div className="mt-4 flex items-center gap-2">
                <a
                  href={p.link}
                  className="rounded-lg border border-slate-700 bg-slate-800 px-3 py-1.5 text-sm font-semibold text-slate-100 transition group-hover:-translate-y-[2px] hover:border-slate-600"
                >
                  Open
                </a>
              </div>
            </motion.article>
          ))}
        </div>
      </section>

      {/* ABOUT */}
      <section id="about" className="mx-auto max-w-6xl px-5 py-10">
        <div className="grid grid-cols-1 items-start gap-6 md:grid-cols-2">
          <motion.div
            initial={{ opacity: 0, y: 16 }}
            whileInView={{ opacity: 1, y: 0 }}
            viewport={{ once: true, amount: 0.4 }}
            transition={{ duration: 0.55 }}
          >
            <h2 className="text-2xl font-bold">About</h2>
            <p className="mt-2 max-w-prose text-slate-300">
              I'm an EE student at SFSU interested in embedded systems, control, and power conversion. I like building small,
              practical systems and documenting what I learn. This site focuses on clarity, speed, and subtle motion.
            </p>
            <ul className="mt-4 grid grid-cols-2 gap-2 text-sm text-slate-300/90">
              <li className="rounded-lg border border-slate-800 bg-slate-900/60 px-3 py-2">Python, C, C++</li>
              <li className="rounded-lg border border-slate-800 bg-slate-900/60 px-3 py-2">STM32, PWM/ADC</li>
              <li className="rounded-lg border border-slate-800 bg-slate-900/60 px-3 py-2">MATLAB/Simulink</li>
              <li className="rounded-lg border border-slate-800 bg-slate-900/60 px-3 py-2">PSpice, Xilinx</li>
            </ul>
          </motion.div>

          <motion.div
            initial={{ opacity: 0, y: 16 }}
            whileInView={{ opacity: 1, y: 0 }}
            viewport={{ once: true, amount: 0.4 }}
            transition={{ duration: 0.55, delay: 0.12 }}
            className="rounded-2xl border border-slate-800 bg-slate-900/60 p-5"
          >
            <h3 className="text-lg font-semibold">Highlights</h3>
            <ul className="mt-2 list-disc space-y-1 pl-5 text-sm text-slate-300">
              <li>Teleoperation system (Quanser Omni) with joint-space control & PID tuning</li>
              <li>Music Transcriber (Python/FFT) — real-time frequency analysis</li>
              <li>DC–DC buck controller (STM32) — ripple & efficiency testing</li>
            </ul>
          </motion.div>
        </div>
      </section>

      {/* CONTACT */}
      <section id="contact" className="mx-auto max-w-6xl px-5 py-12">
        <motion.div
          initial={{ opacity: 0, y: 16 }}
          whileInView={{ opacity: 1, y: 0 }}
          viewport={{ once: true, amount: 0.4 }}
          transition={{ duration: 0.55 }}
          className="rounded-3xl border border-slate-800 bg-gradient-to-br from-slate-900/80 to-slate-900/50 p-6 shadow-xl" >
          <div className="flex flex-col items-start justify-between gap-6 md:flex-row md:items-center">
            <div>
              <h2 className="text-2xl font-bold">Contact</h2>
              <p className="mt-1 max-w-prose text-slate-300">Email me and I'll reply as soon as I can. You can also find me on GitHub or LinkedIn.</p>
            </div>
            <div className="flex flex-col gap-2">
              <a href="mailto:jchua100103@gmail.com" className="rounded-xl bg-sky-500 px-4 py-2 text-center font-semibold text-slate-950 transition hover:-translate-y-[2px] hover:bg-sky-400">Email</a>
              <a href="https://github.com/yourusername" target="_blank" className="rounded-xl border border-slate-700 bg-slate-900 px-4 py-2 text-center font-semibold text-slate-100 transition hover:-translate-y-[2px]">GitHub</a>
              <a href="https://linkedin.com/in/yourprofile" target="_blank" className="rounded-xl border border-slate-700 bg-slate-900 px-4 py-2 text-center font-semibold text-slate-100 transition hover:-translate-y-[2px]">LinkedIn</a>
            </div>
          </div>
        </motion.div>
      </section>

      <Footer />
    </div>
  );
}

function Header({ sections }: { sections: { id: string; label: string }[] }) {
  return (
    <header className="sticky top-0 z-50 w-full border-b border-slate-800/80 bg-slate-950/70 backdrop-blur supports-[backdrop-filter]:bg-slate-950/50">
      <div className="mx-auto flex max-w-6xl items-center justify-between px-5 py-3">
        <a href="#home" className="text-sm font-extrabold tracking-wider text-slate-100">JOHN CHUA</a>
        <nav className="flex items-center gap-2">
          {sections.map((s) => (
            <a key={s.id} href={`#${s.id}`} className="rounded-lg px-3 py-1.5 text-sm font-semibold text-slate-300 transition hover:bg-slate-800/70 hover:text-white">
              {s.label}
            </a>
          ))}
          <a href="/resume.pdf" target="_blank" className="rounded-lg px-3 py-1.5 text-sm font-semibold text-slate-300 transition hover:bg-slate-800/70 hover:text-white">
            Resume
          </a>
        </nav>
      </div>
    </header>
  );
}

function Footer() {
  return (
    <footer className="border-t border-slate-800/80">
      <div className="mx-auto flex max-w-6xl items-center justify-between px-5 py-6 text-sm text-slate-400">
        <span>© {new Date().getFullYear()} John Chua</span>
        <span>Built with React, Tailwind & Framer Motion</span>
      </div>
    </footer>
  );
}
