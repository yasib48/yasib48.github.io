<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game Developer Portfolio</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            font-family: 'Inter', sans-serif;
        }
        html {
            scroll-behavior: smooth;
        }
        .project-card {
            transition: all 0.4s ease;
        }
        .project-card:hover {
            transform: translateY(-8px);
        }
        .project-card img {
            transition: filter 0.4s ease;
            filter: grayscale(30%);
        }
        .project-card:hover img {
            filter: grayscale(0%);
        }
        .modal-overlay {
            animation: fadeIn 0.3s ease;
        }
        .modal-content {
            animation: slideUp 0.3s ease;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        @keyframes slideUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .skill-tag {
            transition: all 0.2s ease;
        }
        .skill-tag:hover {
            background-color: #000;
            color: #fff;
        }
        .admin-panel {
            transition: all 0.4s ease;
        }
        .admin-tab {
            transition: all 0.2s ease;
        }
        .admin-tab.active {
            background-color: #000;
            color: #fff;
        }
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #e5e5e5;
        }
        ::-webkit-scrollbar-thumb {
            background: #888;
            border-radius: 4px;
        }
    </style>
</head>
<body class="bg-gray-100 text-gray-800">
    <!-- Navigation -->
    <nav class="fixed top-0 left-0 right-0 bg-gray-100/95 backdrop-blur-sm z-40 border-b border-gray-300">
        <div class="max-w-6xl mx-auto px-6 py-4 flex justify-between items-center">
            <a href="#hero" id="nav-logo" class="text-xl font-bold tracking-tight">GAMEDEV<span class="text-gray-400">.portfolio</span></a>
            <div class="flex items-center gap-6">
                <a href="#about" class="text-sm font-medium hover:text-gray-500 transition-colors">About</a>
                <a href="#projects" class="text-sm font-medium hover:text-gray-500 transition-colors">Projects</a>
                <button onclick="toggleAdmin()" class="text-sm font-medium text-gray-400 hover:text-black transition-colors">Admin</button>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="hero" class="min-h-screen flex items-center justify-center bg-black text-white relative overflow-hidden">
        <div class="absolute inset-0 opacity-20">
            <div class="absolute top-20 left-20 w-64 h-64 border border-white/30 rotate-45"></div>
            <div class="absolute bottom-20 right-20 w-48 h-48 border border-white/30 rotate-12"></div>
            <div class="absolute top-1/2 left-1/3 w-32 h-32 border border-white/20 -rotate-12"></div>
        </div>
        <div class="text-center z-10 px-6">
            <p id="hero-subtitle" class="text-gray-400 uppercase tracking-widest text-sm mb-4">Game Developer & Designer</p>
            <h1 id="hero-title" class="text-5xl md:text-7xl font-extrabold mb-6 tracking-tight">John Doe</h1>
            <p id="hero-description" class="text-xl md:text-2xl text-gray-300 max-w-2xl mx-auto mb-8">Crafting immersive gaming experiences through innovative design and cutting-edge technology</p>
            <a href="#projects" id="hero-button" class="inline-block border-2 border-white px-8 py-3 font-semibold hover:bg-white hover:text-black transition-all duration-300">View My Work</a>
        </div>
        <div class="absolute bottom-10 left-1/2 -translate-x-1/2 animate-bounce">
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
            </svg>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-24 bg-gray-100">
        <div class="max-w-6xl mx-auto px-6">
            <div class="grid md:grid-cols-2 gap-16 items-center">
                <div>
                    <h2 id="about-title" class="text-4xl font-bold mb-6">About Me</h2>
                    <p id="about-text1" class="text-gray-600 text-lg leading-relaxed mb-6">
                        I'm a passionate game developer with over 8 years of experience creating engaging gaming experiences. From indie mobile games to AAA console titles, I bring creativity and technical expertise to every project.
                    </p>
                    <p id="about-text2" class="text-gray-600 text-lg leading-relaxed mb-8">
                        My journey in game development started with modding classic games and evolved into a career spanning multiple platforms and genres. I specialize in gameplay programming, level design, and creating memorable player experiences.
                    </p>
                    <div id="social-links" class="flex gap-4">
                        <!-- Social links will be rendered here -->
                    </div>
                </div>
                <div>
                    <h3 id="skills-title" class="text-xl font-bold mb-4">Skills & Technologies</h3>
                    <div id="skills-container" class="flex flex-wrap gap-3">
                        <!-- Skills will be rendered here -->
                    </div>
                    <div class="mt-8 p-6 bg-gray-100">
                        <h4 id="experience-title" class="font-bold mb-3">Experience Highlights</h4>
                        <ul id="experience-list" class="space-y-2 text-gray-600">
                            <!-- Experience items will be rendered here -->
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="py-24 bg-gray-200">
        <div class="max-w-6xl mx-auto px-6">
            <div class="text-center mb-16">
                <h2 id="projects-title" class="text-4xl font-bold mb-4">My Projects</h2>
                <p id="projects-subtitle" class="text-gray-600 text-lg">A collection of games I've developed and contributed to</p>
            </div>
            <div id="projectsGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Projects will be rendered here -->
            </div>
        </div>
    </section>

    <!-- Project Modal -->
    <div id="projectModal" class="fixed inset-0 z-50 hidden">
        <div class="modal-overlay absolute inset-0 bg-black/80" onclick="closeModal()"></div>
        <div class="modal-content absolute inset-4 md:inset-10 lg:inset-20 bg-gray-100 overflow-y-auto">
            <button onclick="closeModal()" class="absolute top-4 right-4 w-10 h-10 bg-black text-white flex items-center justify-center hover:bg-gray-800 transition-colors z-10">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
                </svg>
            </button>
            <div id="modalContent" class="p-8 md:p-12">
                <!-- Modal content will be rendered here -->
            </div>
        </div>
    </div>

    <!-- Admin Panel -->
    <div id="adminPanel" class="fixed inset-0 z-50 hidden">
        <div class="absolute inset-0 bg-black/80" onclick="toggleAdmin()"></div>
        <div class="admin-panel absolute right-0 top-0 bottom-0 w-full max-w-2xl bg-gray-100 overflow-y-auto">
            <div class="p-8">
                <div class="flex justify-between items-center mb-6">
                    <h2 class="text-2xl font-bold">Admin Panel</h2>
                    <button onclick="toggleAdmin()" class="w-10 h-10 border border-black flex items-center justify-center hover:bg-black hover:text-white transition-all">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
                        </svg>
                    </button>
                </div>

                <!-- Admin Tabs -->
                <div class="flex gap-2 mb-8">
                    <button onclick="switchAdminTab('projects')" id="tab-projects" class="admin-tab px-4 py-2 border border-black font-medium active">Projects</button>
                    <button onclick="switchAdminTab('content')" id="tab-content" class="admin-tab px-4 py-2 border border-black font-medium">Site Content</button>
                </div>

                <!-- Projects Tab -->
                <div id="admin-projects" class="admin-tab-content">
                    <!-- Add/Edit Form -->
                    <form id="projectForm" class="mb-12">
                        <h3 class="text-lg font-bold mb-4" id="formTitle">Add New Project</h3>
                        <input type="hidden" id="editId">
                        
                        <div class="space-y-4">
                            <div>
                                <label class="block text-sm font-medium mb-1">Project Title *</label>
                                <input type="text" id="title" required class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium mb-1">Short Description *</label>
                                <input type="text" id="shortDesc" required class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium mb-1">Full Description *</label>
                                <textarea id="fullDesc" rows="4" required class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none"></textarea>
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium mb-1">Thumbnail Image</label>
                                <input type="file" id="thumbnail" accept="image/*" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                                <p class="text-xs text-gray-500 mt-1">Or enter URL below</p>
                                <input type="text" id="thumbnailUrl" placeholder="https://example.com/image.jpg" class="w-full border border-gray-300 px-4 py-2 mt-2 focus:border-black focus:outline-none">
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium mb-1">Screenshots (URLs, one per line)</label>
                                <textarea id="screenshots" rows="3" placeholder="https://example.com/screenshot1.jpg&#10;https://example.com/screenshot2.jpg" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none"></textarea>
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium mb-1">Videos (YouTube/Vimeo embed URLs, one per line)</label>
                                <textarea id="videos" rows="2" placeholder="https://www.youtube.com/embed/VIDEO_ID&#10;https://player.vimeo.com/video/VIDEO_ID" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none"></textarea>
                                <p class="text-xs text-gray-500 mt-1">Use embed URLs (e.g., youtube.com/embed/...)</p>
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium mb-1">Technologies (comma separated)</label>
                                <input type="text" id="technologies" placeholder="Unity, C#, Blender" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium mb-1">Platforms (comma separated)</label>
                                <input type="text" id="platforms" placeholder="PC, Mobile, Console" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium mb-1">Year</label>
                                <input type="text" id="year" placeholder="2024" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium mb-1">Download Link</label>
                                <input type="text" id="downloadLink" placeholder="Direct download link for the demo" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                            </div>
                            
                            <div class="flex gap-4 pt-4">
                                <button type="submit" class="flex-1 bg-black text-white py-3 font-semibold hover:bg-gray-800 transition-colors">Save Project</button>
                                <button type="button" onclick="resetForm()" class="px-6 py-3 border border-black font-semibold hover:bg-gray-100 transition-colors">Cancel</button>
                            </div>
                        </div>
                    </form>

                    <!-- Projects List -->
                    <div>
                        <h3 class="text-lg font-bold mb-4">Existing Projects</h3>
                        <div id="adminProjectList" class="space-y-4">
                            <!-- Projects list will be rendered here -->
                        </div>
                    </div>
                </div>

                <!-- Site Content Tab -->
                <div id="admin-content" class="admin-tab-content hidden">
                    <form id="contentForm" class="space-y-8">
                        
                        <!-- Logo Section -->
                        <div class="border-b border-gray-300 pb-6">
                            <h3 class="text-lg font-bold mb-4">🏷️ Logo</h3>
                            <div>
                                <label class="block text-sm font-medium mb-1">Logo Text</label>
                                <input type="text" id="content-logo" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                            </div>
                        </div>

                        <!-- Hero Section -->
                        <div class="border-b border-gray-300 pb-6">
                            <h3 class="text-lg font-bold mb-4">🦸 Hero Section</h3>
                            <div class="space-y-4">
                                <div>
                                    <label class="block text-sm font-medium mb-1">Subtitle</label>
                                    <input type="text" id="content-hero-subtitle" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-1">Title (Your Name)</label>
                                    <input type="text" id="content-hero-title" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-1">Description</label>
                                    <textarea id="content-hero-description" rows="2" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none"></textarea>
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-1">Button Text</label>
                                    <input type="text" id="content-hero-button" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                                </div>
                            </div>
                        </div>

                        <!-- About Section -->
                        <div class="border-b border-gray-300 pb-6">
                            <h3 class="text-lg font-bold mb-4">👤 About Section</h3>
                            <div class="space-y-4">
                                <div>
                                    <label class="block text-sm font-medium mb-1">Section Title</label>
                                    <input type="text" id="content-about-title" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-1">Paragraph 1</label>
                                    <textarea id="content-about-text1" rows="3" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none"></textarea>
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-1">Paragraph 2</label>
                                    <textarea id="content-about-text2" rows="3" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none"></textarea>
                                </div>
                            </div>
                        </div>

                        <!-- Social Links -->
                        <div class="border-b border-gray-300 pb-6">
                            <h3 class="text-lg font-bold mb-4">🔗 Social Links</h3>
                            <div class="space-y-4">
                                <div>
                                    <label class="block text-sm font-medium mb-1">GitHub URL</label>
                                    <input type="text" id="content-social-github" placeholder="https://github.com/username" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-1">LinkedIn URL</label>
                                    <input type="text" id="content-social-linkedin" placeholder="https://linkedin.com/in/username" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-1">Twitter URL</label>
                                    <input type="text" id="content-social-twitter" placeholder="https://twitter.com/username" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                                </div>
                            </div>
                        </div>

                        <!-- Skills Section -->
                        <div class="border-b border-gray-300 pb-6">
                            <h3 class="text-lg font-bold mb-4">🛠️ Skills</h3>
                            <div class="space-y-4">
                                <div>
                                    <label class="block text-sm font-medium mb-1">Skills Title</label>
                                    <input type="text" id="content-skills-title" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-1">Skills (comma separated)</label>
                                    <textarea id="content-skills-list" rows="2" placeholder="Unity, Unreal Engine, C#, C++, Blender" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none"></textarea>
                                </div>
                            </div>
                        </div>

                        <!-- Experience Section -->
                        <div class="border-b border-gray-300 pb-6">
                            <h3 class="text-lg font-bold mb-4">📊 Experience Highlights</h3>
                            <div class="space-y-4">
                                <div>
                                    <label class="block text-sm font-medium mb-1">Experience Title</label>
                                    <input type="text" id="content-experience-title" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-1">Experience Items (one per line)</label>
                                    <textarea id="content-experience-list" rows="4" placeholder="15+ Published Games&#10;5M+ Downloads Worldwide&#10;Award-Winning Developer" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none"></textarea>
                                </div>
                            </div>
                        </div>

                        <!-- Projects Section -->
                        <div class="border-b border-gray-300 pb-6">
                            <h3 class="text-lg font-bold mb-4">🎮 Projects Section</h3>
                            <div class="space-y-4">
                                <div>
                                    <label class="block text-sm font-medium mb-1">Section Title</label>
                                    <input type="text" id="content-projects-title" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-1">Section Subtitle</label>
                                    <input type="text" id="content-projects-subtitle" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                                </div>
                            </div>
                        </div>

                        <!-- Footer Section -->
                        <div class="border-b border-gray-300 pb-6">
                            <h3 class="text-lg font-bold mb-4">📝 Footer</h3>
                            <div class="space-y-4">
                                <div>
                                    <label class="block text-sm font-medium mb-1">Copyright Text</label>
                                    <input type="text" id="content-footer-copyright" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-1">Footer Tagline</label>
                                    <input type="text" id="content-footer-tagline" class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none">
                                </div>
                            </div>
                        </div>

                        <button type="submit" class="w-full bg-black text-white py-3 font-semibold hover:bg-gray-800 transition-colors">Save All Content</button>
                    </form>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-black text-white py-12">
        <div class="max-w-6xl mx-auto px-6 text-center">
            <p id="footer-copyright" class="text-gray-400 mb-4">© 2024 Game Developer Portfolio. All rights reserved.</p>
            <p id="footer-tagline" class="text-sm text-gray-500">Built with passion for gaming</p>
        </div>
    </footer>

    <script>
        // Default Site Content
        let siteContent = {
            logo: "GAMEDEV<span class='text-gray-400'>.portfolio</span>",
            hero: {
                subtitle: "Game Developer & Designer",
                title: "John Doe",
                description: "Crafting immersive gaming experiences through innovative design and cutting-edge technology",
                button: "View My Work"
            },
            about: {
                title: "About Me",
                text1: "I'm a passionate game developer with over 8 years of experience creating engaging gaming experiences. From indie mobile games to AAA console titles, I bring creativity and technical expertise to every project.",
                text2: "My journey in game development started with modding classic games and evolved into a career spanning multiple platforms and genres. I specialize in gameplay programming, level design, and creating memorable player experiences."
            },
            social: {
                github: "#",
                linkedin: "#",
                twitter: "#"
            },
            skills: {
                title: "Skills & Technologies",
                list: ["Unity", "Unreal Engine", "C#", "C++", "Blender", "Photoshop", "3D Modeling", "Level Design", "Shader Programming", "AI Systems", "Multiplayer", "Mobile Games"]
            },
            experience: {
                title: "Experience Highlights",
                list: ["15+ Published Games", "5M+ Downloads Worldwide", "Award-Winning Indie Developer", "Game Jam Organizer"]
            },
            projects: {
                title: "My Projects",
                subtitle: "A collection of games I've developed and contributed to"
            },
            footer: {
                copyright: "© 2024 Game Developer Portfolio. All rights reserved.",
                tagline: "Built with passion for gaming"
            }
        };

        // Sample Projects Data
        let projects = [
            {
                id: 1,
                title: "Cosmic Odyssey",
                shortDesc: "A space exploration RPG with procedurally generated galaxies",
                fullDesc: "Cosmic Odyssey is an expansive space exploration RPG where players navigate through procedurally generated galaxies, discover alien civilizations, and uncover the mysteries of the universe. The game features a deep crafting system, real-time space combat, and a branching narrative with multiple endings.",
                thumbnail: "https://images.unsplash.com/photo-1614732414444-096e5f1122d5?w=600&h=400&fit=crop",
                screenshots: [
                    "https://images.unsplash.com/photo-1614732414444-096e5f1122d5?w=800&h=500&fit=crop",
                    "https://images.unsplash.com/photo-1516339901601-2e1b62dc0c45?w=800&h=500&fit=crop"
                ],
                videos: [
                    "https://www.youtube.com/embed/dQw4w9WgXcQ"
                ],
                technologies: ["Unreal Engine 5", "C++", "Blueprints", "Houdini"],
                platforms: ["PC", "PlayStation 5", "Xbox Series X"],
                year: "2024",
                downloadLink: "#"
            },
            {
                id: 2,
                title: "Shadow Realm",
                shortDesc: "Dark fantasy action game with tactical combat",
                fullDesc: "Shadow Realm is a dark fantasy action game that combines souls-like combat with tactical party management. Players lead a group of cursed warriors through a corrupted kingdom, facing challenging bosses and making moral choices that shape the world.",
                thumbnail: "https://images.unsplash.com/photo-1538481199705-c710c4e965fc?w=600&h=400&fit=crop",
                screenshots: [
                    "https://images.unsplash.com/photo-1538481199705-c710c4e965fc?w=800&h=500&fit=crop",
                    "https://images.unsplash.com/photo-1511512578047-dfb367046420?w=800&h=500&fit=crop"
                ],
                videos: [],
                technologies: ["Unity", "C#", "Blender", "Substance Painter"],
                platforms: ["PC", "Nintendo Switch"],
                year: "2023",
                downloadLink: "#"
            },
            {
                id: 3,
                title: "Pixel Runner",
                shortDesc: "Endless runner with retro pixel art aesthetics",
                fullDesc: "Pixel Runner is a fast-paced endless runner featuring beautiful pixel art graphics and chiptune music. Players dash through procedurally generated levels, collect power-ups, and compete for high scores on global leaderboards.",
                thumbnail: "https://images.unsplash.com/photo-1550745165-9bc0b252726f?w=600&h=400&fit=crop",
                screenshots: [
                    "https://images.unsplash.com/photo-1550745165-9bc0b252726f?w=800&h=500&fit=crop",
                    "https://images.unsplash.com/photo-1551103782-8ab07afd45c1?w=800&h=500&fit=crop"
                ],
                videos: [
                    "https://www.youtube.com/embed/dQw4w9WgXcQ"
                ],
                technologies: ["Unity", "C#", "Aseprite"],
                platforms: ["iOS", "Android"],
                year: "2023",
                downloadLink: "#"
            },
            {
                id: 4,
                title: "Neon City",
                shortDesc: "Cyberpunk puzzle platformer set in a dystopian future",
                fullDesc: "Neon City is a cyberpunk-themed puzzle platformer where players hack their way through a dystopian metropolis. Solve intricate puzzles, avoid security systems, and uncover corporate conspiracies in this visually stunning adventure.",
                thumbnail: "https://images.unsplash.com/photo-1545569341-9eb8b30979d9?w=600&h=400&fit=crop",
                screenshots: [
                    "https://images.unsplash.com/photo-1545569341-9eb8b30979d9?w=800&h=500&fit=crop"
                ],
                videos: [],
                technologies: ["Godot", "GDScript", "Photoshop"],
                platforms: ["PC", "Mac", "Linux"],
                year: "2022",
                downloadLink: ""
            },
            {
                id: 5,
                title: "Farm Tales",
                shortDesc: "Cozy farming simulation with magical creatures",
                fullDesc: "Farm Tales is a cozy farming simulation game where players cultivate magical crops, befriend mythical creatures, and build a thriving farm community. Features seasonal events, crafting, and heartwarming storylines.",
                thumbnail: "https://images.unsplash.com/photo-1500595046743-cd271d694d30?w=600&h=400&fit=crop",
                screenshots: [
                    "https://images.unsplash.com/photo-1500595046743-cd271d694d30?w=800&h=500&fit=crop",
                    "https://images.unsplash.com/photo-1416879595882-3373a0480b5b?w=800&h=500&fit=crop"
                ],
                videos: [
                    "https://www.youtube.com/embed/dQw4w9WgXcQ"
                ],
                technologies: ["Unity", "C#", "Spine 2D"],
                platforms: ["PC", "iOS", "Android"],
                year: "2022",
                downloadLink: "#"
            },
            {
                id: 6,
                title: "Battle Arena",
                shortDesc: "Competitive multiplayer arena shooter",
                fullDesc: "Battle Arena is a fast-paced competitive multiplayer arena shooter featuring unique character abilities, strategic team play, and intense 5v5 matches. Climb the ranked ladder and prove your skills against players worldwide.",
                thumbnail: "https://images.unsplash.com/photo-1542751371-adc38448a05e?w=600&h=400&fit=crop",
                screenshots: [
                    "https://images.unsplash.com/photo-1542751371-adc38448a05e?w=800&h=500&fit=crop"
                ],
                videos: [],
                technologies: ["Unreal Engine 4", "C++", "Dedicated Servers"],
                platforms: ["PC"],
                year: "2021",
                downloadLink: "#"
            }
        ];

        // Load site content from localStorage
        function loadSiteContent() {
            const saved = localStorage.getItem('portfolioSiteContent');
            if (saved) {
                siteContent = JSON.parse(saved);
            }
            renderSiteContent();
            populateContentForm();
        }

        // Save site content to localStorage
        function saveSiteContent() {
            localStorage.setItem('portfolioSiteContent', JSON.stringify(siteContent));
        }

        // Render site content to page
        function renderSiteContent() {
            // Logo
            document.getElementById('nav-logo').innerHTML = siteContent.logo;

            // Hero
            document.getElementById('hero-subtitle').textContent = siteContent.hero.subtitle;
            document.getElementById('hero-title').textContent = siteContent.hero.title;
            document.getElementById('hero-description').textContent = siteContent.hero.description;
            document.getElementById('hero-button').textContent = siteContent.hero.button;

            // About
            document.getElementById('about-title').textContent = siteContent.about.title;
            document.getElementById('about-text1').textContent = siteContent.about.text1;
            document.getElementById('about-text2').textContent = siteContent.about.text2;

            // Social Links
            document.getElementById('social-links').innerHTML = `
                <a href="${siteContent.social.github}" target="_blank" class="w-10 h-10 border border-black flex items-center justify-center hover:bg-black hover:text-white transition-all">
                    <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
                </a>
                <a href="${siteContent.social.linkedin}" target="_blank" class="w-10 h-10 border border-black flex items-center justify-center hover:bg-black hover:text-white transition-all">
                    <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
                </a>
                <a href="${siteContent.social.twitter}" target="_blank" class="w-10 h-10 border border-black flex items-center justify-center hover:bg-black hover:text-white transition-all">
                    <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/></svg>
                </a>
            `;

            // Skills
            document.getElementById('skills-title').textContent = siteContent.skills.title;
            document.getElementById('skills-container').innerHTML = siteContent.skills.list.map(skill => `
                <span class="skill-tag px-4 py-2 border border-black text-sm font-medium cursor-default">${skill}</span>
            `).join('');

            // Experience
            document.getElementById('experience-title').textContent = siteContent.experience.title;
            document.getElementById('experience-list').innerHTML = siteContent.experience.list.map(item => `
                <li class="flex items-center gap-2">
                    <span class="w-2 h-2 bg-black"></span>
                    ${item}
                </li>
            `).join('');

            // Projects Section
            document.getElementById('projects-title').textContent = siteContent.projects.title;
            document.getElementById('projects-subtitle').textContent = siteContent.projects.subtitle;

            // Footer
            document.getElementById('footer-copyright').textContent = siteContent.footer.copyright;
            document.getElementById('footer-tagline').textContent = siteContent.footer.tagline;
        }

        // Populate content form with current values
        function populateContentForm() {
            document.getElementById('content-logo').value = siteContent.logo.replace(/<[^>]*>/g, '').replace('.portfolio', '<span>.portfolio</span>');
            document.getElementById('content-hero-subtitle').value = siteContent.hero.subtitle;
            document.getElementById('content-hero-title').value = siteContent.hero.title;
            document.getElementById('content-hero-description').value = siteContent.hero.description;
            document.getElementById('content-hero-button').value = siteContent.hero.button;
            document.getElementById('content-about-title').value = siteContent.about.title;
            document.getElementById('content-about-text1').value = siteContent.about.text1;
            document.getElementById('content-about-text2').value = siteContent.about.text2;
            document.getElementById('content-social-github').value = siteContent.social.github;
            document.getElementById('content-social-linkedin').value = siteContent.social.linkedin;
            document.getElementById('content-social-twitter').value = siteContent.social.twitter;
            document.getElementById('content-skills-title').value = siteContent.skills.title;
            document.getElementById('content-skills-list').value = siteContent.skills.list.join(', ');
            document.getElementById('content-experience-title').value = siteContent.experience.title;
            document.getElementById('content-experience-list').value = siteContent.experience.list.join('\n');
            document.getElementById('content-projects-title').value = siteContent.projects.title;
            document.getElementById('content-projects-subtitle').value = siteContent.projects.subtitle;
            document.getElementById('content-footer-copyright').value = siteContent.footer.copyright;
            document.getElementById('content-footer-tagline').value = siteContent.footer.tagline;
        }

        // Handle content form submission
        document.getElementById('contentForm').addEventListener('submit', function(e) {
            e.preventDefault();

            const logoText = document.getElementById('content-logo').value;
            const logoParts = logoText.split('.');
            siteContent.logo = logoParts.length > 1 
                ? `${logoParts[0]}<span class='text-gray-400'>.${logoParts.slice(1).join('.')}</span>`
                : logoText;

            siteContent.hero.subtitle = document.getElementById('content-hero-subtitle').value;
            siteContent.hero.title = document.getElementById('content-hero-title').value;
            siteContent.hero.description = document.getElementById('content-hero-description').value;
            siteContent.hero.button = document.getElementById('content-hero-button').value;
            siteContent.about.title = document.getElementById('content-about-title').value;
            siteContent.about.text1 = document.getElementById('content-about-text1').value;
            siteContent.about.text2 = document.getElementById('content-about-text2').value;
            siteContent.social.github = document.getElementById('content-social-github').value;
            siteContent.social.linkedin = document.getElementById('content-social-linkedin').value;
            siteContent.social.twitter = document.getElementById('content-social-twitter').value;
            siteContent.skills.title = document.getElementById('content-skills-title').value;
            siteContent.skills.list = document.getElementById('content-skills-list').value.split(',').map(s => s.trim()).filter(s => s);
            siteContent.experience.title = document.getElementById('content-experience-title').value;
            siteContent.experience.list = document.getElementById('content-experience-list').value.split('\n').map(s => s.trim()).filter(s => s);
            siteContent.projects.title = document.getElementById('content-projects-title').value;
            siteContent.projects.subtitle = document.getElementById('content-projects-subtitle').value;
            siteContent.footer.copyright = document.getElementById('content-footer-copyright').value;
            siteContent.footer.tagline = document.getElementById('content-footer-tagline').value;

            saveSiteContent();
            renderSiteContent();
            alert('Site content saved successfully!');
        });

        // Switch admin tabs
        function switchAdminTab(tab) {
            document.querySelectorAll('.admin-tab-content').forEach(el => el.classList.add('hidden'));
            document.querySelectorAll('.admin-tab').forEach(el => el.classList.remove('active'));
            
            document.getElementById(`admin-${tab}`).classList.remove('hidden');
            document.getElementById(`tab-${tab}`).classList.add('active');
        }

        // Load projects from localStorage if available
        function loadProjects() {
            const saved = localStorage.getItem('portfolioProjects');
            if (saved) {
                projects = JSON.parse(saved);
            }
            renderProjects();
            renderAdminList();
        }

        // Save projects to localStorage
        function saveProjects() {
            localStorage.setItem('portfolioProjects', JSON.stringify(projects));
        }

        // Render projects grid
        function renderProjects() {
            const grid = document.getElementById('projectsGrid');
            grid.innerHTML = projects.map(project => `
                <div class="project-card bg-gray-50 cursor-pointer shadow-lg" onclick="openModal(${project.id})">
                    <div class="aspect-video overflow-hidden">
                        <img src="${project.thumbnail}" alt="${project.title}" class="w-full h-full object-cover">
                    </div>
                    <div class="p-6">
                        <div class="flex justify-between items-start mb-2">
                            <h3 class="text-xl font-bold">${project.title}</h3>
                            <span class="text-sm text-gray-400">${project.year}</span>
                        </div>
                        <p class="text-gray-600 mb-4">${project.shortDesc}</p>
                        <div class="flex flex-wrap gap-2">
                            ${project.platforms.slice(0, 3).map(p => `
                                <span class="text-xs px-2 py-1 bg-gray-100 text-gray-600">${p}</span>
                            `).join('')}
                        </div>
                    </div>
                </div>
            `).join('');
        }

        // Open project modal
        function openModal(id) {
            const project = projects.find(p => p.id === id);
            if (!project) return;

            const modal = document.getElementById('projectModal');
            const content = document.getElementById('modalContent');

            content.innerHTML = `
                <div class="grid lg:grid-cols-2 gap-8">
                    <div>
                        <div id="mainMedia" class="w-full aspect-video mb-4 bg-black">
                            <img src="${project.thumbnail}" alt="${project.title}" class="w-full h-full object-cover">
                        </div>
                        ${(project.screenshots && project.screenshots.length > 0) || (project.videos && project.videos.length > 0) ? `
                            <div class="grid grid-cols-4 gap-2">
                                ${project.videos ? project.videos.map(v => `
                                    <div class="relative w-full aspect-video cursor-pointer hover:opacity-80 transition-opacity bg-gray-800 flex items-center justify-center" onclick="showVideo('${v}')">
                                        <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 24 24">
                                            <path d="M8 5v14l11-7z"/>
                                        </svg>
                                        <span class="absolute bottom-1 right-1 text-xs text-white bg-black/70 px-1">VIDEO</span>
                                    </div>
                                `).join('') : ''}
                                ${project.screenshots ? project.screenshots.slice(0, 4 - (project.videos ? project.videos.length : 0)).map(s => `
                                    <img src="${s}" alt="Screenshot" class="w-full aspect-video object-cover cursor-pointer hover:opacity-80 transition-opacity" onclick="showImage('${s}')">
                                `).join('') : ''}
                            </div>
                        ` : ''}
                    </div>
                    <div>
                        <div class="flex items-center gap-4 mb-4">
                            <h2 class="text-3xl font-bold">${project.title}</h2>
                            <span class="text-gray-400">${project.year}</span>
                        </div>
                        <p class="text-gray-600 text-lg leading-relaxed mb-6">${project.fullDesc}</p>
                        
                        <div class="mb-6">
                            <h4 class="font-bold mb-3">Technologies</h4>
                            <div class="flex flex-wrap gap-2">
                                ${project.technologies.map(t => `
                                    <span class="px-3 py-1 border border-black text-sm">${t}</span>
                                `).join('')}
                            </div>
                        </div>
                        
                        <div class="mb-6">
                            <h4 class="font-bold mb-3">Platforms</h4>
                            <div class="flex flex-wrap gap-2">
                                ${project.platforms.map(p => `
                                    <span class="px-3 py-1 bg-black text-white text-sm">${p}</span>
                                `).join('')}
                            </div>
                        </div>
                        
                        <div class="flex gap-4">
                            ${project.downloadLink ? `
                                <a href="${project.downloadLink}" download class="flex items-center gap-2 px-6 py-3 bg-black text-white font-semibold hover:bg-gray-800 transition-colors">
                                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4"></path>
                                    </svg>
                                    Download Demo
                                </a>
                            ` : ''}
                        </div>
                    </div>
                </div>
            `;

            modal.classList.remove('hidden');
            document.body.style.overflow = 'hidden';
        }

        // Close modal
        function closeModal() {
            document.getElementById('projectModal').classList.add('hidden');
            document.body.style.overflow = '';
        }

        // Show video in main media area
        function showVideo(url) {
            const mainMedia = document.getElementById('mainMedia');
            mainMedia.innerHTML = `<iframe src="${url}" class="w-full h-full" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>`;
        }

        // Show image in main media area
        function showImage(url) {
            const mainMedia = document.getElementById('mainMedia');
            mainMedia.innerHTML = `<img src="${url}" alt="Screenshot" class="w-full h-full object-cover">`;
        }

        // Toggle admin panel
        function toggleAdmin() {
            const panel = document.getElementById('adminPanel');
            panel.classList.toggle('hidden');
            if (!panel.classList.contains('hidden')) {
                document.body.style.overflow = 'hidden';
            } else {
                document.body.style.overflow = '';
                resetForm();
            }
        }

        // Render admin projects list
        function renderAdminList() {
            const list = document.getElementById('adminProjectList');
            list.innerHTML = projects.map(project => `
                <div class="flex items-center gap-4 p-4 border border-gray-200">
                    <img src="${project.thumbnail}" alt="${project.title}" class="w-16 h-16 object-cover">
                    <div class="flex-1">
                        <h4 class="font-bold">${project.title}</h4>
                        <p class="text-sm text-gray-500">${project.year}</p>
                    </div>
                    <button onclick="editProject(${project.id})" class="p-2 hover:bg-gray-100 transition-colors">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z"></path>
                        </svg>
                    </button>
                    <button onclick="deleteProject(${project.id})" class="p-2 hover:bg-red-100 text-red-600 transition-colors">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16"></path>
                        </svg>
                    </button>
                </div>
            `).join('');
        }

        // Edit project
        function editProject(id) {
            const project = projects.find(p => p.id === id);
            if (!project) return;

            switchAdminTab('projects');

            document.getElementById('formTitle').textContent = 'Edit Project';
            document.getElementById('editId').value = id;
            document.getElementById('title').value = project.title;
            document.getElementById('shortDesc').value = project.shortDesc;
            document.getElementById('fullDesc').value = project.fullDesc;
            document.getElementById('thumbnailUrl').value = project.thumbnail;
            document.getElementById('screenshots').value = project.screenshots ? project.screenshots.join('\n') : '';
            document.getElementById('videos').value = project.videos ? project.videos.join('\n') : '';
            document.getElementById('technologies').value = project.technologies.join(', ');
            document.getElementById('platforms').value = project.platforms.join(', ');
            document.getElementById('year').value = project.year;
            document.getElementById('downloadLink').value = project.downloadLink || '';

            document.querySelector('.admin-panel').scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Delete project
        function deleteProject(id) {
            if (confirm('Are you sure you want to delete this project?')) {
                projects = projects.filter(p => p.id !== id);
                saveProjects();
                renderProjects();
                renderAdminList();
            }
        }

        // Reset form
        function resetForm() {
            document.getElementById('formTitle').textContent = 'Add New Project';
            document.getElementById('projectForm').reset();
            document.getElementById('editId').value = '';
        }

        // Handle form submission
        document.getElementById('projectForm').addEventListener('submit', async function(e) {
            e.preventDefault();

            const editId = document.getElementById('editId').value;
            const thumbnailFile = document.getElementById('thumbnail').files[0];
            let thumbnailUrl = document.getElementById('thumbnailUrl').value;

            // Handle file upload - convert to base64
            if (thumbnailFile) {
                thumbnailUrl = await new Promise((resolve) => {
                    const reader = new FileReader();
                    reader.onload = (e) => resolve(e.target.result);
                    reader.readAsDataURL(thumbnailFile);
                });
            }

            const projectData = {
                id: editId ? parseInt(editId) : Date.now(),
                title: document.getElementById('title').value,
                shortDesc: document.getElementById('shortDesc').value,
                fullDesc: document.getElementById('fullDesc').value,
                thumbnail: thumbnailUrl || 'https://images.unsplash.com/photo-1511512578047-dfb367046420?w=600&h=400&fit=crop',
                screenshots: document.getElementById('screenshots').value.split('\n').filter(s => s.trim()),
                videos: document.getElementById('videos').value.split('\n').filter(v => v.trim()),
                technologies: document.getElementById('technologies').value.split(',').map(t => t.trim()).filter(t => t),
                platforms: document.getElementById('platforms').value.split(',').map(p => p.trim()).filter(p => p),
                year: document.getElementById('year').value || new Date().getFullYear().toString(),
                downloadLink: document.getElementById('downloadLink').value
            };

            if (editId) {
                const index = projects.findIndex(p => p.id === parseInt(editId));
                if (index !== -1) {
                    projects[index] = projectData;
                }
            } else {
                projects.unshift(projectData);
            }

            saveProjects();
            renderProjects();
            renderAdminList();
            resetForm();
            alert('Project saved successfully!');
        });

        // Close modal on escape key
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') {
                closeModal();
                if (!document.getElementById('adminPanel').classList.contains('hidden')) {
                    toggleAdmin();
                }
            }
        });

        // Initialize
        loadSiteContent();
        loadProjects();
    </script>
</body>
</html>
