  Moving Apartments? Here’s How I Rebuilt My Mac Setup (and My Life) in One Script

  Moving is one of life’s most stressful events. It’s a chaotic whirlwind of boxes, logistics, and the daunting task of making a new, empty space feel like
  home. Recently, I found myself in the middle of this chaos, moving to a new apartment. But I also had another move to make: migrating my entire digital life
  from my trusty M1 MacBook Pro to a brand-new M4 model.

  In the past, setting up a new machine was a multi-day affair filled with forgotten settings, manual downloads, and endless configuration tweaks. This time,
  it was different. What if I told you that setting up my new Mac took less time than unpacking the kitchen?

  This wasn't magic. It was the result of treating my personal setup like a professional automation project: version-controlled, repeatable, and ready to
  deploy anywhere. Here’s how I did it.

  [IMAGE: A stylish, minimalist desk with a new MacBook Pro M4, surrounded by a few neatly stacked moving boxes.]

  The Philosophy: Your Setup as Code

  As automation and AI enthusiasts, we live by the principle of "Don't Repeat Yourself." We write scripts and build workflows to avoid redundant work. So why
  do we spend hours, or even days, manually rebuilding our own environments every time we get a new machine?

  The answer is to apply the "Infrastructure as Code" philosophy to your personal workspace. Your Mac's configuration shouldn't be a fragile sandcastle,
  rebuilt from memory each time. It should be a blueprint—a single source of truth that can be deployed consistently and automatically. This is the core idea
  behind a dotfiles repository.

  [IMAGE: A split-screen image showing a messy, chaotic desktop on one side and a clean, organized terminal on the other.]

  The Blueprint: A Tour of My One-Click Mac

  My entire digital life now lives in a single Git repository. It’s a collection of scripts and configuration files (or "dotfiles") that define everything
  from my terminal aliases to the GUI apps I use for work. Here’s a breakdown of the key components.

  The Foundation: A Centralized Dotfiles Repository

  At the heart of it all is a Git repository that holds my digital blueprint. By structuring my configurations in logical folders (brew/, zsh/, scripts/), I
  keep everything organized and easy to find. This repository is the single source of truth for my setup on any machine.

  Moving a file is as simple as git mv, and every change is tracked. This isn't just a backup; it's a living, version-controlled history of my entire
  environment.

  [IMAGE: A screenshot of the dotfiles repository structure in a code editor, showing the brew, zsh, and scripts folders.]

  The Universal Toolkit: Homebrew & the Magic Brewfile

  Manually downloading and installing software is a thing of the past. My setup relies on a single brewfile that defines every piece of software I need.
  Homebrew, the package manager for macOS, reads this file and automates the installation of everything.

  This isn't just for command-line tools. My brewfile manages:
   - CLI Tools: Modern, high-performance tools like eza (a better ls), btop (a resource monitor), and trivy (a vulnerability scanner).
   - GUI Apps: All my daily drivers, especially productivity powerhouses like Notion, Raycast, and the Arc browser, are installed automatically.
   - Mac App Store Apps: Using mas, even App Store software like Perplexity and Gemini Desktop is automated.
   - Fonts: All my favorite programming fonts, like JetBrains Mono and Fira Code, are installed automatically.

  [IMAGE: A code snippet from the brewfile, highlighting a few interesting tools like Notion, Raycast, and Arc.]

  The Engine Room: A Supercharged .zshrc

  For anyone deep in automation and IT, the terminal is your command center. My .zshrc file is the engine that powers my productivity, turning a simple shell
  into a command powerhouse. With over 150 aliases and 20+ functions, common tasks are reduced to a few keystrokes.

  For example, gs runs git status, klf tails Kubernetes logs, and dprune safely cleans up Docker resources. The setup is powered by a lightning-fast Starship 
  prompt, which gives me all the context I need (Git branch, Kubernetes context, etc.) in a clean, minimal interface. The best part? It’s the exact same on
  every machine.

  [IMAGE: A beautiful screenshot of the terminal showing the custom Starship prompt and maybe the output of a custom alias.]

  The AI Co-pilot: Integrating Next-Gen Tools

  A modern workflow isn't complete without a suite of AI tools. My setup integrates them directly, ensuring I have an AI co-pilot ready for any task, whether
  it's research, scripting, or automation.

  My toolkit includes:
   - Google Gemini & Perplexity: For quick research, brainstorming, and on-demand code generation.
   - Fabric AI & Gemini CLI: For more powerful, terminal-based tasks like summarizing technical documents or interacting with AI workflows on the fly.

  [IMAGE: A conceptual image of a brain with glowing neural networks connecting to the logos of Google Gemini and Perplexity.]

  The Automation Suite: One Script to Rule Them All

  This is where it all comes together. A single script, install.sh, automates the entire setup process. Thanks to some clever shell scripting, it can be run
  with a single curl command.

  sh -c "$(curl -fsSL https://raw.githubusercontent.com/RohiRIK/dotfiles/main/scripts/install.sh)"

  This one-liner automatically clones the repository and executes the installer, which handles everything: installing Homebrew, running the brewfile, linking
  the .zshrc, and even setting up a weekly cron job to keep all my apps updated. It’s the "one-click" button for my entire digital life.

  [IMAGE: A terminal window showing the output of the install.sh script running, with its "INFO" messages.]

  Key Takeaways

  Building this system was an investment, but the payoff is immense. Here are the core principles:
   - Treat your setup as code. Your environment should be declarative, version-controlled, and repeatable.
   - Automate everything. If you have to do a setup task more than once, script it.
   - Use a single source of truth. A dotfiles repository prevents configuration drift between machines.
   - Document your process. A good README.md is a gift to your future self.

  Conclusion

  Moving to a new apartment finally feels like coming home once your pictures are on the wall. In the same way, my new M4 MacBook Pro instantly felt like my
  machine the moment the install.sh script finished. All my tools, aliases, and settings were exactly where they should be.

  The freedom and peace of mind that come from this level of automation are hard to overstate. Whether I’m upgrading hardware, recovering a machine, or just
  helping a colleague, my entire workflow is now as portable as the laptop it runs on. If you haven't started your own dotfiles journey, I hope this inspires
  you to begin. Start small, automate one thing, and build from there.

  [IMAGE: A person smiling and relaxing in their new, organized apartment, with their perfectly set up MacBook in the foreground.]

  ---

  Thanks for reading, and happy automating!

  Rohi Rikman

  💼 Connect on LinkedIn (https://www.linkedin.com/in/rohi-rikman-48831b239) | 💻 Follow on GitHub (https://github.com/RohiRIK)
