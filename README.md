import React from "react";
import { motion } from "framer-motion";
import { Github, Code, Star, Globe } from "lucide-react";

export default function GithubProfile() {
  return (
    <div className="min-h-screen w-full bg-gradient-to-br from-gray-900 via-black to-gray-950 text-white p-6 flex flex-col items-center">
      {/* Header */}
      <motion.div
        initial={{ opacity: 0, y: -20 }}
        animate={{ opacity: 1, y: 0 }}
        className="text-center mb-10"
      >
        <h1 className="text-4xl font-bold mb-2">Himanshu Gangwar</h1>
        <p className="text-gray-300 text-lg">
          Full-Stack Developer • MERN / Next.js / Node.js Enthusiast
        </p>
      </motion.div>

      {/* Contribution Graph */}
      <motion.div
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ delay: 0.3 }}
        className="w-full max-w-4xl mb-10"
      >
        <div className="bg-gray-800/40 p-4 rounded-2xl shadow-xl">
          <h2 className="text-xl mb-4 font-semibold flex items-center gap-2">
            <Code className="w-5 h-5" /> GitHub Contributions
          </h2>
          <img
            src="https://ghchart.rshah.org/FFFFFF/himanshugangwar"
            alt="GitHub Contribution Chart"
            className="w-full rounded-lg border border-gray-700"
          />
        </div>
      </motion.div>

      {/* Skills Section */}
      <motion.div
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ delay: 0.5 }}
        className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 max-w-5xl w-full mb-10"
      >
        {["JavaScript", "TypeScript", "React.js", "Next.js", "Node.js", "MongoDB", "Express.js", "TailwindCSS", "Git/GitHub"].map(
          (skill, i) => (
            <motion.div
              key={i}
              whileHover={{ scale: 1.05 }}
              className="p-5 bg-gray-800/50 rounded-2xl shadow-lg flex items-center gap-3 border border-gray-700"
            >
              <Code className="w-5 h-5 text-blue-400" /> {skill}
            </motion.div>
          )
        )}
      </motion.div>

      {/* Top Projects */}
      <div className="w-full max-w-5xl">
        <h2 className="text-2xl font-semibold mb-6 flex items-center gap-2">
          <Star className="w-6 h-6 text-yellow-400" /> Top 3 Projects
        </h2>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
          {[
            {
              title: "Portfolio Website",
              desc: "A modern animated developer portfolio built using React & Framer Motion.",
              link: "https://github.com/himanshugangwar/portfolio",
            },
            {
              title: "E-Commerce App",
              desc: "Full-stack MERN e-commerce app with cart, auth, and payment system.",
              link: "https://github.com/himanshugangwar/ecommerce",
            },
            {
              title: "Next.js Blog Platform",
              desc: "SEO-optimized blog with MDX support built with Next.js 14.",
              link: "https://github.com/himanshugangwar/blog-platform",
            },
          ].map((project, i) => (
            <motion.a
              key={i}
              href={project.link}
              target="_blank"
              rel="noopener noreferrer"
              whileHover={{ scale: 1.05 }}
              className="block bg-gray-800/50 p-6 rounded-2xl shadow-lg border border-gray-700 hover:border-blue-500 transition-all"
            >
              <h3 className="text-xl font-semibold mb-2 flex items-center gap-2">
                <Github className="w-5 h-5" /> {project.title}
              </h3>
              <p className="text-gray-300 text-sm">{project.desc}</p>
              <div className="mt-3 flex items-center gap-1 text-blue-400">
                <Globe className="w-4 h-4" /> View Project
              </div>
            </motion.a>
          ))}
        </div>
      </div>
    </div>
  );
}
