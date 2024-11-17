import React from 'react';
import { GithubIcon, LinkedinIcon, Code, Activity, Terminal } from 'lucide-react';

const GithubProfile = () => {
  const techStack = {
    "Languages": [
      {
        name: "C",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg",
        proficiency: 85,
        backgroundColor: "rgba(40, 40, 40, 0.8)",
        link: "https://www.cprogramming.com/"
      },
      {
        name: "Java",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg",
        proficiency: 90,
        backgroundColor: "rgba(40, 40, 40, 0.8)",
        link: "https://www.java.com"
      },
      {
        name: "JavaScript",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg",
        proficiency: 80,
        backgroundColor: "rgba(40, 40, 40, 0.8)",
        link: "https://developer.mozilla.org/en-US/docs/Web/JavaScript"
      },
      {
        name: "PHP",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg",
        proficiency: 75,
        backgroundColor: "rgba(40, 40, 40, 0.8)",
        link: "https://www.php.net"
      }
    ],
    "Frontend": [
      {
        name: "HTML5",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg",
        proficiency: 95,
        backgroundColor: "rgba(40, 40, 40, 0.8)",
        link: "https://www.w3.org/html/"
      },
      {
        name: "CSS3",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg",
        proficiency: 85,
        backgroundColor: "rgba(40, 40, 40, 0.8)",
        link: "https://www.w3schools.com/css/"
      },
      {
        name: "React",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg",
        proficiency: 80,
        backgroundColor: "rgba(40, 40, 40, 0.8)",
        link: "https://reactjs.org/"
      }
    ],
    "Tools & Technologies": [
      {
        name: "MySQL",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg",
        proficiency: 85,
        backgroundColor: "rgba(40, 40, 40, 0.8)",
        link: "https://www.mysql.com/"
      },
      {
        name: "Git",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg",
        proficiency: 80,
        backgroundColor: "rgba(40, 40, 40, 0.8)",
        link: "https://git-scm.com/"
      },
      {
        name: "Linux",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg",
        proficiency: 75,
        backgroundColor: "rgba(40, 40, 40, 0.8)",
        link: "https://www.linux.org/"
      }
    ]
  };

  const TechCard = ({ tech }) => (
    <a 
      href={tech.link}
      target="_blank"
      rel="noreferrer"
      className="group relative flex flex-col items-center p-4 bg-black rounded-lg border border-zinc-800 hover:border-zinc-600 transition-all duration-300 hover:scale-105"
    >
      <img 
        src={`/api/placeholder/48/48`} 
        alt={tech.name}
        className="w-12 h-12 mb-2 transition-transform duration-300 group-hover:scale-110"
      />
      <span className="text-sm font-medium text-zinc-300 group-hover:text-white">
        {tech.name}
      </span>
      <div className="mt-2 w-full h-1 bg-zinc-800 rounded-full overflow-hidden">
        <div 
          className="h-full bg-gradient-to-r from-zinc-600 to-zinc-400 transition-all duration-500 group-hover:from-zinc-400 group-hover:to-white"
          style={{ width: `${tech.proficiency}%` }}
        />
      </div>
      <span className="absolute top-1 right-1 text-xs text-zinc-500 group-hover:text-zinc-300">
        {tech.proficiency}%
      </span>
    </a>
  );

  return (
    <div className="min-h-screen bg-gradient-to-br from-black via-zinc-900 to-black text-zinc-100 p-8">
      <div className="max-w-4xl mx-auto space-y-12">
        {/* Header */}
        <div className="text-center space-y-4">
          <h1 className="text-4xl font-bold bg-gradient-to-r from-white via-zinc-400 to-white text-transparent bg-clip-text">
            Hi 👋, I'm Kithmini Mayodya
          </h1>
          <h2 className="text-2xl text-zinc-400 hover:text-white transition-colors">
            Software Developer
          </h2>
          <p className="text-zinc-500">
            Undergraduate at University of Colombo School of Computing
          </p>
        </div>

        {/* Connect */}
        <div className="flex justify-center gap-4">
          <a href="https://www.linkedin.com/in/kithmini-herath-584250286" 
             className="p-3 bg-zinc-900 rounded-lg hover:bg-zinc-800 transition-all duration-300 hover:scale-110 border border-zinc-800 hover:border-zinc-700">
            <LinkedinIcon className="w-6 h-6 text-zinc-400 hover:text-white" />
          </a>
          <a href="https://github.com/kithmini11" 
             className="p-3 bg-zinc-900 rounded-lg hover:bg-zinc-800 transition-all duration-300 hover:scale-110 border border-zinc-800 hover:border-zinc-700">
            <GithubIcon className="w-6 h-6 text-zinc-400 hover:text-white" />
          </a>
        </div>

        {/* Tech Stack */}
        {Object.entries(techStack).map(([category, technologies]) => (
          <div key={category} className="space-y-4">
            <h3 className="text-xl font-semibold flex items-center gap-2 text-zinc-200">
              <Code className="w-5 h-5 text-zinc-400" />
              {category}
            </h3>
            <div className="grid grid-cols-2 md:grid-cols-4 gap-4">
              {technologies.map(tech => (
                <TechCard key={tech.name} tech={tech} />
              ))}
            </div>
          </div>
        ))}

        {/* GitHub Stats */}
        <div className="space-y-4">
          <h3 className="text-xl font-semibold flex items-center gap-2 text-zinc-200">
            <Activity className="w-5 h-5 text-zinc-400" />
            GitHub Statistics
          </h3>
          <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
            <div className="p-4 bg-black border border-zinc-800 rounded-lg hover:border-zinc-600 transition-all duration-300">
              <div className="text-sm text-zinc-400">Total Commits</div>
              <div className="text-lg font-semibold">500+</div>
            </div>
            <div className="p-4 bg-black border border-zinc-800 rounded-lg hover:border-zinc-600 transition-all duration-300">
              <div className="text-sm text-zinc-400">Repositories</div>
              <div className="text-lg font-semibold">15+</div>
            </div>
            <div className="p-4 bg-black border border-zinc-800 rounded-lg hover:border-zinc-600 transition-all duration-300">
              <div className="text-sm text-zinc-400">Contributions</div>
              <div className="text-lg font-semibold">1000+</div>
            </div>
          </div>
        </div>

        {/* Footer */}
        <div className="text-center text-sm text-zinc-400">
          <p>Thanks for visiting my profile! 👋</p>
          <div className="mt-2">
            <span className="bg-black px-4 py-2 rounded-full inline-block border border-zinc-800 hover:border-zinc-700 transition-all duration-300">
              Profile Views: 1.5k+
            </span>
          </div>
        </div>
      </div>
    </div>
  );
};

export default GithubProfile;
