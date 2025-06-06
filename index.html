import React, { useState, useEffect } from 'react';

// --- Helper Functions ---
function generateSlug(languageName) {
  return languageName.toLowerCase().replace(/\s+/g, '-');
}

function escapeHtml(unsafe) {
    if (unsafe === null || unsafe === undefined) {
        return '';
    }
    return unsafe
         .replace(/&/g, "&amp;")
         .replace(/</g, "&lt;")
         .replace(/>/g, "&gt;")
         .replace(/"/g, "&quot;")
         .replace(/'/g, "&#039;");
}

function downloadFile(filename, content) {
  const element = document.createElement('a');
  element.setAttribute('href', 'data:text/html;charset=utf-8,' + encodeURIComponent(content));
  element.setAttribute('download', filename);
  document.body.appendChild(element);
  element.click();
  document.body.removeChild(element);
}

// --- Default Data & Placeholders ---
const initialGeneralSettings = {
  languageName: 'Nouveau Langage',
  targetLanguage: 'Langue Cible',
  nativeLanguage: 'Français',
  flagColor1: '#FFFFFF',
  flagColor2: '#0039A6',
  flagColor3: '#D52B1E',
  themePrimary: '#1e3a8a',
  themeSecondary: '#c53030',
  themeAccent: '#5a67d8',
  themeLight: '#f7fafc',
  themeDark: '#2d3748',
  themeBackground: '#f0f5ff',
  themeCardBg: '#ffffff', // For light mode vocab card
  themeRusse: '#c53030', // Color for target language text
  themeFrancais: '#3182ce', // Color for native language text (translation)
};

const initialIndexSettings = {
  introTitle: 'Bienvenue dans votre aventure !',
  introParagraph: 'Découvrez la richesse de cette langue à travers notre méthode progressive et interactive.',
  week1Title: 'Semaine 1 : Les Fondamentaux',
  week1Summary: 'Découverte des 10 premières lettres : А, Б, В, Г, Д, Е, Ё, Ж, З, И...',
  week2Title: 'Semaine 2 : Structures de Base',
  week2Summary: 'Maîtriser les pronoms et comprendre l\'utilisation du verbe être...',
  week3Title: 'Semaine 3 : Communication Élargie',
  week3Summary: 'Apprendre à exprimer ce qu\'on aime et ce qu\'on n\'aime pas...',
  resourcesApps: 'Anki, Duolingo, Memrise',
  resourcesBooks: 'Grammaire pour débutants, Dictionnaire bilingue',
  resourcesWebsites: 'LanguagePod101, Wikipedia',
};

const initialAlphabetSettings = {
  pageTitle: 'Alphabet de la Langue Cible',
  pageSubtitle: 'Un guide simple pour apprendre l\'écriture',
  introBoxTitle: 'À propos de cet alphabet',
  introBoxContent: 'Cet alphabet comporte X lettres. Il tire son nom de...',
  learningTips: 'Commencez par les lettres similaires...\nPratiquez l\'écriture...\nUtilisez des flashcards...',
  // Letter format: LetterMaj;letterMin;[pronunciation];comme "exemple";Type(Identique/Piège/Unique);motCible1,[pronCible1],traduction1|motCible2,[pronCible2],traduction2
  lettersData: `A;a;[a];comme 'ami';Identique;apple,[apəl],pomme|ant,[ænt],fourmi
B;b;[b];comme 'balle';Identique;ball,[bɔːl],balle|banana,[bəˈnɑːnə],banane
C;c;[s];comme 'ceci' AVANT e,i,y;Piège;city,[ˈsɪti],ville|cent,[sɛnt],centime
X;x;[ks];comme 'xylophone';Unique;`,
};

const initialVocabularySettings = {
  pageTitle: 'Vocabulaire de la Langue Cible',
  pageSubtitle: 'Liste complète pour l\'apprentissage',
  searchPlaceholder: 'Rechercher un mot...',
  // Category format: id,DisplayName
  categoriesData: `basics,Bases
greetings,Salutations
numbers,Nombres
food,Nourriture`,
  // Vocab format: targetWord;[pronunciation];nativeTranslation;category1,category2;Nuance (optional)
  wordsData: `Bonjour;[bɔ̃ʒuʁ];Hello;greetings;Formule de politesse courante.
Oui;[wi];Yes;basics;
Non;[nɔ̃];No;basics;
Maison;[mɛzɔ̃];House;basics;Appartient à la catégorie 'logement'.
Un;[œ̃];One;numbers;
Deux;[dø];Two;numbers;`,
};

const initialCourseSettings = {
  pageTitle: 'Cours en 21 Jours',
  progressText: 'jours complétés',
  // Week format: Title;Objective
  weeksData: `Semaine 1: Les Fondamentaux;Se familiariser avec l'alphabet, acquérir les bases de la prononciation...
Semaine 2: Grammaire de Base;Maîtriser les pronoms personnels, conjuguer les verbes...
Semaine 3: Situations Quotidiennes;Apprendre à exprimer ses goûts, commander au restaurant...`,
  // Day format: DayNumber;Title;Objective;
  // Sections format within a day, separated by triple underscore ___
  // SECTION_TYPE|Title (optional)|Content or Data (structured as needed per type)
  // For LetterGrid: LETTER_GRID|Title|L1,p1,ex1|L2,p2,ex2
  // For VocabList: VOCAB_LIST|Title|W1,p1,t1|W2,p2,t2
  // For NoteBox: NOTE_BOX|Title|Content
  // For Exercise: EXERCISE|Title|Content
  // For Dialogue: DIALOGUE|S1:Line1R,Line1T|S2:Line2R,Line2T
  // For RecapList: RECAP_LIST|Title|Item1|Item2
  daysData: [
    // Day 1
    `1;Découverte de l'Alphabet (Partie 1);Se familiariser avec les dix premières lettres.
TEXT_SECTION|Introduction|Bienvenue au premier jour !
LETTER_GRID|Les 10 premières lettres|A,a,[a],ami|B,b,[b],balle|C,c,[s],ceci
VOCAB_LIST|Vocabulaire de base|Oui,[wi],Yes|Non,[nɔ̃],No
EXERCISE|Exercice d'écriture|Tracez chaque lettre 10 fois.
FOCUS_BOX|Focus Culturel: Origine de l'alphabet|L'alphabet de cette langue a une histoire riche...`,
    // Day 2
    `2;Découverte de l'Alphabet (Partie 2);Apprendre les dix lettres suivantes.
TEXT_SECTION|Révision|Revoyons les lettres d'hier.
LETTER_GRID|Les 10 lettres suivantes|D,d,[d],dent|E,e,[ə],le
VOCAB_LIST|Objets courants|Table,[tabl],Table|Chaise,[ʃɛz],Chair
EXERCISE|Association|Reliez les sons aux lettres.
FOCUS_BOX|Phonétique: Sons spécifiques|Certains sons peuvent être nouveaux...`,
    // ... Add placeholders for more days up to 21. For brevity, only 2 are shown here.
    // Day 7 (example for week recap)
    `7;Révision Semaine 1;Consolider les acquis.
TEXT_SECTION|Récapitulatif|Nous avons couvert l'alphabet et les salutations.
RECAP_LIST|Acquis de la semaine|Alphabet complet|Salutations de base|Nombres 1-10
EXERCISE|Quiz rapide|Testez vos connaissances de la semaine.
FOCUS_BOX|Conseils d'étude|Pratiquez 15 minutes chaque jour.`,
    // Day 21
    `21;Révision Générale et Bilan;Consolider tous les acquis des trois semaines.
TEXT_SECTION|Félicitations!|Vous avez terminé le programme de base!
RECAP_LIST|Compétences acquises|Compréhension orale de base|Expression orale simple|Lecture de textes courts
EXERCISE|Auto-évaluation|Évaluez vos progrès et identifiez les points à renforcer.
FOCUS_BOX|Prochaines étapes|Continuez votre apprentissage avec des ressources intermédiaires. Parlez avec des natifs!`,
  ].join('\n__DAY_SEPARATOR__\n'), // Use a unique separator for days
  congratsTitle: 'Félicitations !',
  congratsMessage: 'Bravo pour votre persévérance ! Vous avez maintenant acquis les bases solides.',
  congratsAchievements: 'Maîtrise de l\'alphabet\nVocabulaire de base\nStructures grammaticales essentielles',
};


// --- React Component ---
export default function App() {
  const [generalSettings, setGeneralSettings] = useState(initialGeneralSettings);
  const [indexSettings, setIndexSettings] = useState(initialIndexSettings);
  const [alphabetSettings, setAlphabetSettings] = useState(initialAlphabetSettings);
  const [vocabularySettings, setVocabularySettings] = useState(initialVocabularySettings);
  const [courseSettings, setCourseSettings] = useState(initialCourseSettings);

  const [activeTab, setActiveTab] = useState('general');

  const handleInputChange = (setter, group, field, value) => {
    setter(prev => ({ ...prev, [field]: value }));
  };
  
  const handleTextareaChange = (setter, field, value) => {
    setter(prev => ({ ...prev, [field]: value }));
  };


  // --- Generation Functions ---

  const generateIndexHTML = () => {
    const slug = generateSlug(generalSettings.targetLanguage);
    const html = `
<!DOCTYPE html>
<html lang="${generalSettings.nativeLanguage.slice(0,2).toLowerCase()}">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>${escapeHtml(generalSettings.languageName)} - Guide Complet</title>
    <style>
        :root {
            --primary: ${escapeHtml(generalSettings.themePrimary)};
            --secondary: ${escapeHtml(generalSettings.themeSecondary)};
            --accent: ${escapeHtml(generalSettings.themeAccent)};
            --light: ${escapeHtml(generalSettings.themeLight)};
            --dark: ${escapeHtml(generalSettings.themeDark)};
            --background: ${escapeHtml(generalSettings.themeBackground)};
            --russe: ${escapeHtml(generalSettings.themeRusse)}; /* Target language text */
            --francais: ${escapeHtml(generalSettings.themeFrancais)}; /* Native language text */
        }
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; line-height: 1.6; color: var(--dark); background: var(--background); }
        .container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }
        header { background: linear-gradient(135deg, var(--primary), var(--accent)); color: white; padding: 30px 0; text-align: center; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); position: relative; }
        header h1 { font-size: 2.5rem; margin-bottom: 15px; }
        .flag-colors { display: flex; height: 10px; margin: 20px auto 0; width: 200px; border-radius: 5px; overflow: hidden; box-shadow: 0 2px 4px rgba(0,0,0,0.2); }
        .flag-white { background: ${escapeHtml(generalSettings.flagColor1)}; flex: 1; }
        .flag-blue { background: ${escapeHtml(generalSettings.flagColor2)}; flex: 1; }
        .flag-red { background: ${escapeHtml(generalSettings.flagColor3)}; flex: 1; }
        .navigation { background: white; padding: 20px 0; box-shadow: 0 2px 4px rgba(0,0,0,0.1); margin-bottom: 30px; }
        .nav-buttons { display: flex; justify-content: center; gap: 20px; flex-wrap: wrap; }
        .nav-btn { background: var(--primary); color: white; padding: 12px 24px; text-decoration: none; border-radius: 8px; font-weight: 500; transition: all 0.3s ease; border: none; cursor: pointer; }
        .nav-btn:hover { background: var(--accent); transform: translateY(-2px); }
        .nav-btn.active { background: var(--secondary); }
        .main-content { background: white; border-radius: 10px; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); padding: 30px; margin-bottom: 30px; }
        .intro-section { text-align: center; margin-bottom: 40px; }
        .intro-section h2 { color: var(--primary); font-size: 2rem; margin-bottom: 20px; }
        .intro-section p { font-size: 1.1rem; max-width: 800px; margin: 0 auto 30px; }
        .features-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px; margin-top: 40px; }
        .feature-card { background: var(--light); padding: 30px; border-radius: 10px; text-align: center; transition: transform 0.3s ease; }
        .feature-card:hover { transform: translateY(-5px); }
        .feature-icon { font-size: 3rem; margin-bottom: 20px; }
        .feature-card h3 { color: var(--primary); margin-bottom: 15px; }
        .program-overview { margin-top: 50px; }
        .week-section { background: white; border: 1px solid #e2e8f0; border-radius: 10px; margin-bottom: 20px; overflow: hidden; }
        .week-header { background: var(--primary); color: white; padding: 15px 25px; cursor: pointer; display: flex; justify-content: space-between; align-items: center; }
        .week-content { padding: 20px 25px; display: none; }
        .week-content.active { display: block; }
        .day-item { padding: 15px; border-bottom: 1px solid #e2e8f0; transition: background-color 0.3s ease; }
        .day-item:hover { background-color: var(--light); }
        .day-item:last-child { border-bottom: none; }
        .day-title { font-weight: 600; color: var(--primary); margin-bottom: 5px; }
        .day-description { color: var(--dark); font-size: 0.95rem; }
        footer { background: var(--primary); color: white; text-align: center; padding: 30px 0; margin-top: 50px; }
        .theme-toggle { position: absolute; right: 20px; top: 20px; background: transparent; border: none; color: white; font-size: 1.5rem; cursor: pointer; z-index: 1001; }
        @media (max-width: 768px) {
            .nav-buttons { flex-direction: column; align-items: center; }
            .nav-btn { width: 80%; text-align: center; }
            header h1 { font-size: 2rem; }
            .features-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <button id="theme-toggle" class="theme-toggle">🌙</button>
            <h1>${escapeHtml(generalSettings.languageName)}</h1>
            <p>Votre guide complet pour maîtriser la langue ${escapeHtml(generalSettings.targetLanguage.toLowerCase())}</p>
            <div class="flag-colors">
                <div class="flag-white"></div>
                <div class="flag-blue"></div>
                <div class="flag-red"></div>
            </div>
        </div>
    </header>

    <nav class="navigation">
        <div class="container">
            <div class="nav-buttons">
                <a href="index.html" class="nav-btn active">🏠 Accueil</a>
                <a href="alphabet_${slug}.html" class="nav-btn">🔤 Alphabet</a>
                <a href="vocabulaire_${slug}.html" class="nav-btn">📚 Vocabulaire</a>
                <a href="cours-21-jours_${slug}.html" class="nav-btn">📅 Programme 21 jours</a>
            </div>
        </div>
    </nav>

    <main>
        <div class="container">
            <div class="main-content">
                <section class="intro-section">
                    <h2>${escapeHtml(indexSettings.introTitle)}</h2>
                    <p>${escapeHtml(indexSettings.introParagraph)}</p>
                    <div class="features-grid">
                        <div class="feature-card">
                            <div class="feature-icon">🔤</div>
                            <h3>Alphabet</h3>
                            <p>Maîtrisez l'alphabet avec notre guide interactif.</p>
                            <a href="alphabet_${slug}.html" class="nav-btn" style="margin-top: 15px; display: inline-block;">Commencer</a>
                        </div>
                        <div class="feature-card">
                            <div class="feature-icon">📚</div>
                            <h3>Vocabulaire Essentiel</h3>
                            <p>Mots classés par thème avec prononciation et traduction.</p>
                            <a href="vocabulaire_${slug}.html" class="nav-btn" style="margin-top: 15px; display: inline-block;">Explorer</a>
                        </div>
                        <div class="feature-card">
                            <div class="feature-icon">📅</div>
                            <h3>Programme 21 Jours</h3>
                            <p>Un parcours structuré pour acquérir les bases en trois semaines.</p>
                            <a href="cours-21-jours_${slug}.html" class="nav-btn" style="margin-top: 15px; display: inline-block;">Découvrir</a>
                        </div>
                    </div>
                </section>

                <section id="programme" class="program-overview">
                    <h2 style="text-align: center; color: var(--primary); margin-bottom: 30px;">Aperçu du Programme d'Apprentissage en 21 Jours</h2>
                    <div class="week-section">
                        <div class="week-header" onclick="toggleWeek('week1')">
                            <h3>${escapeHtml(indexSettings.week1Title)}</h3> <span>▼</span>
                        </div>
                        <div class="week-content" id="week1"><p>${escapeHtml(indexSettings.week1Summary)}</p></div>
                    </div>
                    <div class="week-section">
                        <div class="week-header" onclick="toggleWeek('week2')">
                            <h3>${escapeHtml(indexSettings.week2Title)}</h3> <span>▼</span>
                        </div>
                        <div class="week-content" id="week2"><p>${escapeHtml(indexSettings.week2Summary)}</p></div>
                    </div>
                    <div class="week-section">
                        <div class="week-header" onclick="toggleWeek('week3')">
                            <h3>${escapeHtml(indexSettings.week3Title)}</h3> <span>▼</span>
                        </div>
                        <div class="week-content" id="week3"><p>${escapeHtml(indexSettings.week3Summary)}</p></div>
                    </div>
                    <div style="text-align: center; margin-top: 30px;">
                        <a href="cours-21-jours_${slug}.html" class="nav-btn" style="background-color: var(--secondary);">Accéder au Programme Complet</a>
                    </div>
                </section>

                <section id="ressources" style="margin-top: 50px;">
                     <h2 style="text-align: center; color: var(--primary); margin-bottom: 30px;">Ressources Complémentaires</h2>
                     <div class="features-grid">
                        <div class="feature-card"> <div class="feature-icon">📱</div> <h3>Applications Recommandées</h3> <p>${escapeHtml(indexSettings.resourcesApps)}</p> </div>
                        <div class="feature-card"> <div class="feature-icon">📖</div> <h3>Livres et Manuels</h3> <p>${escapeHtml(indexSettings.resourcesBooks)}</p> </div>
                        <div class="feature-card"> <div class="feature-icon">🌐</div> <h3>Sites Web</h3> <p>${escapeHtml(indexSettings.resourcesWebsites)}</p> </div>
                     </div>
                </section>
            </div>
        </div>
    </main>

    <footer>
        <div class="container">
            <p>&copy; ${new Date().getFullYear()} ${escapeHtml(generalSettings.languageName)}</p>
            <p>Créé pour les passionnés de la langue ${escapeHtml(generalSettings.targetLanguage.toLowerCase())}</p>
        </div>
    </footer>

    <script>
        function toggleWeek(weekId) {
            const content = document.getElementById(weekId);
            const header = content.previousElementSibling;
            const arrow = header.querySelector('span');
            document.querySelectorAll('.week-content.active').forEach(openContent => {
                if (openContent.id !== weekId) {
                    openContent.classList.remove('active');
                    openContent.previousElementSibling.querySelector('span').textContent = '▼';
                }
            });
            content.classList.toggle('active');
            arrow.textContent = content.classList.contains('active') ? '▲' : '▼';
        }
        
        const themeToggleBtn = document.getElementById('theme-toggle');
        function loadTheme() {
            const currentTheme = localStorage.getItem('theme-${slug}');
            if (currentTheme) {
                document.body.classList.add(currentTheme);
                if (themeToggleBtn) themeToggleBtn.textContent = currentTheme === 'dark-mode' ? '☀️' : '🌙';
            } else { // Default to light mode if no theme is stored
                 if (themeToggleBtn) themeToggleBtn.textContent = '🌙';
            }
        }
        if (themeToggleBtn) {
            themeToggleBtn.addEventListener('click', () => {
                document.body.classList.toggle('dark-mode');
                let theme = 'light-mode';
                if (document.body.classList.contains('dark-mode')) {
                    theme = 'dark-mode';
                    themeToggleBtn.textContent = '☀️';
                } else {
                    themeToggleBtn.textContent = '🌙';
                }
                localStorage.setItem('theme-${slug}', theme);
            });
        }
        document.addEventListener('DOMContentLoaded', loadTheme);
    </script>
</body>
</html>`;
    downloadFile(`index.html`, html);
  };

  const generateAlphabetHTML = () => {
    const slug = generateSlug(generalSettings.targetLanguage);
    let lettersHTML = '';
    const letterRows = alphabetSettings.lettersData.split('\n').filter(row => row.trim() !== '');
    letterRows.forEach(row => {
      const parts = row.split(';');
      if (parts.length >= 5) {
        const [charMaj, charMin, pronunciation, example, type, wordExamplesStr = ''] = parts;
        let examplesHTML = '';
        if (wordExamplesStr) {
          examplesHTML = wordExamplesStr.split('|').map(ex => {
            const [word, pron, trans] = ex.split(',');
            return `<div class="word-example">
                        <span class="word">${escapeHtml(word)}</span>
                        <span class="word-pronunciation">${escapeHtml(pron)}</span>
                        <span class="word-translation">- ${escapeHtml(trans)}</span>
                    </div>`;
          }).join('');
        }

        let cardClass = '';
        let typeText = '';
        if (type.toLowerCase() === 'identique') { cardClass = 'similar'; typeText = 'Identique'; }
        else if (type.toLowerCase() === 'piège') { cardClass = 'different'; typeText = 'Piège'; }
        else { cardClass = 'unique'; typeText = 'Unique';}

        lettersHTML += `
<div class="letter-card ${cardClass}" data-letter="${escapeHtml(charMaj)} ${escapeHtml(charMin)}">
    <span class="letter-type">${escapeHtml(typeText)}</span>
    <div class="letter-display">
        <span>${escapeHtml(charMaj)}</span>
        <span>${escapeHtml(charMin)}</span>
    </div>
    <div class="pronunciation">${escapeHtml(pronunciation)}</div>
    <div class="example">${escapeHtml(example)}</div>
    ${examplesHTML ? `<div class="word-examples">${examplesHTML}</div>` : ''}
</div>`;
      }
    });

    const html = `
<!DOCTYPE html>
<html lang="${generalSettings.nativeLanguage.slice(0,2).toLowerCase()}">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>${escapeHtml(alphabetSettings.pageTitle)} - ${escapeHtml(generalSettings.languageName)}</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Noto+Sans:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: ${escapeHtml(generalSettings.themePrimary)};
            --secondary: ${escapeHtml(generalSettings.themeSecondary)};
            --accent: ${escapeHtml(generalSettings.themeAccent)};
            --light: ${escapeHtml(generalSettings.themeLight)};
            --dark: ${escapeHtml(generalSettings.themeDark)};
            --russe: ${escapeHtml(generalSettings.themeRusse)}; /* Target language text */
            --francais: ${escapeHtml(generalSettings.themeFrancais)}; /* Native language text */
            --background: ${escapeHtml(generalSettings.themeBackground)};
            --card-bg: ${escapeHtml(generalSettings.themeCardBg)};
            --info-icon-color: var(--francais);
            --modal-bg: rgba(0,0,0,0.5);
            --modal-content-bg: var(--card-bg);
        }
        body.dark-mode {
            --primary: #3b82f6; --secondary: #ef4444; --accent: #818cf8;
            --light: #1f2937; --dark: #f9fafb; --background: #111827;
            --russe: #f87171; --francais: #60a5fa; --card-bg: #1e293b;
             --info-icon-color: var(--francais);
            --modal-bg: rgba(0,0,0,0.7); --modal-content-bg: var(--card-bg);
        }
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body { font-family: 'Inter', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; line-height: 1.6; color: var(--dark); background: var(--background); transition: background 0.3s, color 0.3s; }
        .container { max-width: 1200px; margin: 0 auto; padding: 0 1rem; }
        header { background: linear-gradient(135deg, var(--primary), var(--accent)); color: white; padding: 2rem 0; text-align: center; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); position: relative; }
        header h1 { font-size: 2.5rem; margin-bottom: 0.5rem; }
        .theme-toggle { position: absolute; right: 20px; top: 20px; background: transparent; border: none; color: white; font-size: 1.5rem; cursor: pointer; }
        .navigation { background: white; padding: 15px 0; box-shadow: 0 2px 4px rgba(0,0,0,0.1); margin-bottom: 30px; }
        .nav-buttons { display: flex; justify-content: center; gap: 15px; flex-wrap: wrap; }
        .nav-btn { background: var(--primary); color: white; padding: 10px 20px; text-decoration: none; border-radius: 6px; font-weight: 500; transition: all 0.3s ease; font-size: 0.9rem; }
        .nav-btn:hover { background: var(--accent); transform: translateY(-2px); }
        .nav-btn.active { background: var(--secondary); }
        .flag-colors { display: flex; height: 10px; margin: 20px auto 0; width: 200px; border-radius: 5px; overflow: hidden; box-shadow: 0 2px 4px rgba(0,0,0,0.2); }
        .flag-white { background: ${escapeHtml(generalSettings.flagColor1)}; flex: 1; }
        .flag-blue { background: ${escapeHtml(generalSettings.flagColor2)}; flex: 1; }
        .flag-red { background: ${escapeHtml(generalSettings.flagColor3)}; flex: 1; }
        h2 { font-size: 2rem; color: var(--primary); margin: 2rem 0 1rem; border-bottom: 2px solid var(--accent); padding-bottom: 0.5rem; }
        .info-box { background-color: var(--card-bg); border-radius: 10px; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); padding: 1.5rem; margin: 2rem 0; }
        .info-title { font-weight: bold; color: var(--primary); margin-bottom: 1rem; font-size: 1.2rem; }
        .alphabet-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); gap: 1rem; margin: 1.5rem 0; }
        .letter-card { background-color: var(--card-bg); border-radius: 10px; box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); padding: 1.5rem; transition: transform 0.3s ease, box-shadow 0.3s ease; position: relative; overflow: hidden; }
        .letter-card:hover { transform: translateY(-5px); box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2); }
        .letter-card.similar { border-left: 4px solid #38a169; } .letter-card.different { border-left: 4px solid #e53e3e; } .letter-card.unique { border-left: 4px solid #d69e2e; }
        .letter-display { font-size: 3rem; font-weight: bold; color: var(--russe); margin-bottom: 1rem; display: flex; justify-content: space-between; font-family: 'Noto Sans', sans-serif; }
        .pronunciation { font-size: 1.2rem; color: var(--dark); font-style: italic; margin-bottom: 0.5rem; }
        .example { font-size: 1.1rem; color: var(--dark); margin-bottom: 0.5rem; }
        .word-examples { margin-top: 1rem; padding-top: 1rem; border-top: 1px solid #e2e8f0; }
        .word-example { margin-bottom: 0.5rem; } .word { color: var(--russe); font-weight: bold; font-family: 'Noto Sans', sans-serif;} .word-pronunciation { color: var(--dark); font-style: italic; } .word-translation { color: var(--francais); }
        .letter-type { position: absolute; top: 0.5rem; right: 0.5rem; font-size: 0.8rem; padding: 0.2rem 0.5rem; border-radius: 20px; font-weight: bold; }
        .similar .letter-type { background-color: #38a16922; color: #38a169; } .different .letter-type { background-color: #e53e3e22; color: #e53e3e; } .unique .letter-type { background-color: #d69e2e22; color: #d69e2e; }
        .section-tabs { display: flex; overflow-x: auto; margin: 2rem 0 1rem; padding-bottom: 0.5rem; border-bottom: 1px solid #e2e8f0; }
        .section-tab { padding: 0.5rem 1rem; margin-right: 0.5rem; background-color: #e2e8f0; border-radius: 5px 5px 0 0; font-weight: 500; cursor: pointer; white-space: nowrap; }
        .section-tab.active { background-color: var(--primary); color: white; }
        .section-content { display: none; } .section-content.active { display: block; }
        .search-bar { margin: 2rem 0; display: flex; justify-content: center; }
        .search-input { width: 100%; max-width: 500px; padding: 0.75rem 1rem; border: 2px solid var(--primary); border-radius: 25px; font-size: 1rem; outline: none; background-color: var(--card-bg); color: var(--dark); }
        footer { background-color: var(--primary); color: white; text-align: center; padding: 2rem 0; margin-top: 3rem; }
        @media (max-width: 768px) { .alphabet-grid { grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); } h1 { font-size: 2rem; } h2 { font-size: 1.7rem; } .nav-buttons { flex-direction: column; align-items: center; } .nav-btn { width: 90%; text-align: center; margin: 2px 0; } }
        @media (max-width: 480px) { .alphabet-grid { grid-template-columns: 1fr; } .letter-display { font-size: 2.5rem; } }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <button id="theme-toggle" class="theme-toggle">🌙</button>
            <h1>${escapeHtml(alphabetSettings.pageTitle)}</h1>
            <p>${escapeHtml(alphabetSettings.pageSubtitle)}</p>
            <div class="flag-colors">
                <div class="flag-white"></div> <div class="flag-blue"></div> <div class="flag-red"></div>
            </div>
        </div>
    </header>
    <nav class="navigation">
        <div class="container">
            <div class="nav-buttons">
                <a href="index.html" class="nav-btn">🏠 Accueil</a>
                <a href="alphabet_${slug}.html" class="nav-btn active">🔤 Alphabet</a>
                <a href="vocabulaire_${slug}.html" class="nav-btn">📚 Vocabulaire</a>
                <a href="cours-21-jours_${slug}.html" class="nav-btn">📅 Programme 21 jours</a>
            </div>
        </div>
    </nav>
    <div class="container">
        <div class="search-bar">
            <input type="text" class="search-input" id="searchLetters" placeholder="Rechercher une lettre..." oninput="filterLetters()">
        </div>
        <div class="section-tabs">
            <div class="section-tab active" onclick="showSection('all-letters')">Toutes les lettres</div>
            <div class="section-tab" onclick="showSection('similar-letters')">Lettres similaires</div>
            <div class="section-tab" onclick="showSection('different-letters')">Lettres pièges</div>
            <div class="section-tab" onclick="showSection('unique-letters')">Lettres uniques</div>
        </div>
        <div class="info-box">
            <div class="info-title">${escapeHtml(alphabetSettings.introBoxTitle)}</div>
            <p>${escapeHtml(alphabetSettings.introBoxContent.replace(/\n/g, '<br>'))}</p>
        </div>
        <section id="all-letters" class="section-content active">
            <h2>L'alphabet complet</h2>
            <div class="alphabet-grid">${lettersHTML}</div>
        </section>
        <section id="similar-letters" class="section-content">
            <h2>Lettres similaires</h2> <div class="alphabet-grid" id="similar-grid"></div>
        </section>
        <section id="different-letters" class="section-content">
            <h2>Lettres pièges</h2> <div class="alphabet-grid" id="different-grid"></div>
        </section>
        <section id="unique-letters" class="section-content">
            <h2>Lettres uniques</h2> <div class="alphabet-grid" id="unique-grid"></div>
        </section>
        <div class="info-box">
            <div class="info-title">Astuces pour l'apprentissage</div>
            <p>${escapeHtml(alphabetSettings.learningTips.replace(/\n/g, '<br>'))}</p>
        </div>
    </div>
    <footer> <p>Guide d'apprentissage de l'alphabet ${escapeHtml(generalSettings.targetLanguage.toLowerCase())}</p> </footer>
    <script>
        function showSection(sectionId) {
            document.querySelectorAll('.section-content').forEach(s => s.classList.remove('active'));
            document.getElementById(sectionId).classList.add('active');
            document.querySelectorAll('.section-tab').forEach(t => t.classList.remove('active'));
            document.querySelector(\`.section-tab[onclick="showSection('\${sectionId}')"]\`).classList.add('active');
        }
        function filterLetters() {
            const searchTerm = document.getElementById('searchLetters').value.toLowerCase();
            document.querySelectorAll('.letter-card').forEach(card => {
                const letterText = card.dataset.letter.toLowerCase();
                const cardContent = card.textContent.toLowerCase();
                card.style.display = (letterText.includes(searchTerm) || cardContent.includes(searchTerm)) ? '' : 'none';
            });
        }
        function populateCategoryGrids() {
            ['similar', 'different', 'unique'].forEach(type => {
                const grid = document.getElementById(type + '-grid');
                if (!grid) return;
                document.querySelectorAll('#all-letters .letter-card.' + type).forEach(letter => {
                    grid.appendChild(letter.cloneNode(true));
                });
            });
        }
        document.addEventListener('DOMContentLoaded', () => {
            populateCategoryGrids();
            const themeToggleBtn = document.getElementById('theme-toggle');
            function loadTheme() {
                const currentTheme = localStorage.getItem('theme-${slug}');
                if (currentTheme) {
                    document.body.classList.add(currentTheme);
                    if (themeToggleBtn) themeToggleBtn.textContent = currentTheme === 'dark-mode' ? '☀️' : '🌙';
                } else {
                     if (themeToggleBtn) themeToggleBtn.textContent = '🌙';
                }
            }
             if (themeToggleBtn) {
                themeToggleBtn.addEventListener('click', () => {
                    document.body.classList.toggle('dark-mode');
                    let theme = 'light-mode';
                    if (document.body.classList.contains('dark-mode')) {
                        theme = 'dark-mode';
                        themeToggleBtn.textContent = '☀️';
                    } else {
                        themeToggleBtn.textContent = '🌙';
                    }
                    localStorage.setItem('theme-${slug}', theme);
                });
            }
            loadTheme();
        });
    </script>
</body>
</html>`;
    downloadFile(`alphabet_${slug}.html`, html);
  };

  const generateVocabularyHTML = () => {
    const slug = generateSlug(generalSettings.targetLanguage);
    let categoryFiltersHTML = '<button class="category-filter active" data-category="all">Tous</button>';
    const categories = vocabularySettings.categoriesData.split('\n').map(line => {
        const parts = line.split(',');
        return { id: parts[0]?.trim(), name: parts[1]?.trim() };
    }).filter(cat => cat.id && cat.name);

    categories.forEach(cat => {
        categoryFiltersHTML += `<button class="category-filter" data-category="${escapeHtml(cat.id)}">${escapeHtml(cat.name)}</button>`;
    });
    
    const vocabularyArray = vocabularySettings.wordsData.split('\n').filter(row => row.trim() !== '').map(row => {
        const parts = row.split(';');
        return {
            russian: parts[0]?.trim() || '', // target language word
            pronunciation: parts[1]?.trim() || '',
            translation: parts[2]?.trim() || '', // native language translation
            categories: parts[3] ? parts[3].split(',').map(c => c.trim()) : ['basics'],
            nuance: parts[4]?.trim() || ''
        };
    });

    const html = `
<!DOCTYPE html>
<html lang="${generalSettings.nativeLanguage.slice(0,2).toLowerCase()}">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>${escapeHtml(vocabularySettings.pageTitle)} - ${escapeHtml(generalSettings.languageName)}</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Noto+Sans:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: ${escapeHtml(generalSettings.themePrimary)};
            --secondary: ${escapeHtml(generalSettings.themeSecondary)};
            --accent: ${escapeHtml(generalSettings.themeAccent)};
            --light: ${escapeHtml(generalSettings.themeLight)};
            --dark: ${escapeHtml(generalSettings.themeDark)};
            --russe: ${escapeHtml(generalSettings.themeRusse)}; /* Target language text */
            --francais: ${escapeHtml(generalSettings.themeFrancais)}; /* Native language text */
            --background: ${escapeHtml(generalSettings.themeBackground)};
            --card-bg: ${escapeHtml(generalSettings.themeCardBg)};
            --shadow: 0 4px 6px rgba(0,0,0,0.1); --hover-shadow: 0 8px 15px rgba(0,0,0,0.2);
            --border-radius: 8px; --transition: all 0.3s ease;
            --info-icon-color: var(--francais);
            --modal-bg: rgba(0,0,0,0.5); --modal-content-bg: var(--card-bg); --modal-shadow: 0 5px 15px rgba(0,0,0,0.3);
            --border-color: #e2e8f0;
        }
        body.dark-mode {
            --primary: #3b82f6; --secondary: #ef4444; --accent: #818cf8;
            --light: #1f2937; --dark: #f9fafb; --background: #111827;
            --russe: #f87171; --francais: #60a5fa; --card-bg: #1e293b;
            --shadow: 0 4px 6px rgba(0,0,0,0.3); --hover-shadow: 0 8px 15px rgba(0,0,0,0.4);
            --info-icon-color: var(--francais);
            --modal-bg: rgba(0,0,0,0.7); --modal-content-bg: var(--card-bg); --modal-shadow: 0 5px 15px rgba(0,0,0,0.5);
            --border-color: #374151;
        }
        * { box-sizing: border-box; margin:0; padding:0; }
        body { font-family: 'Inter', 'Segoe UI', sans-serif; line-height:1.6; color:var(--dark); background:var(--background); min-height:100vh; transition:var(--transition); }
        .container { max-width:1200px; margin:0 auto; padding:0 20px; }
        header { background:linear-gradient(135deg, var(--primary), var(--accent)); color:white; padding:30px 0; box-shadow:var(--shadow); position:relative; }
        header h1 { font-size:2.5rem; text-align:center; margin-bottom:15px; }
        header p { font-size:1.2rem; text-align:center; opacity:0.9; }
        .theme-toggle { position:absolute; right:20px; top:20px; background:transparent; border:none; color:white; font-size:1.5rem; cursor:pointer; }
        .navigation { background:var(--card-bg); padding:15px 0; box-shadow:0 2px 4px rgba(0,0,0,0.1); margin-bottom:30px; }
        .nav-buttons { display:flex; justify-content:center; gap:15px; flex-wrap:wrap; }
        .nav-btn { background:var(--primary); color:white; padding:10px 20px; text-decoration:none; border-radius:6px; font-weight:500; transition:all 0.3s ease; font-size:0.9rem; }
        .nav-btn:hover { background:var(--accent); transform:translateY(-2px); }
        .nav-btn.active { background:var(--secondary); }
        .flag-colors { display:flex; height:10px; margin:20px auto 0; width:200px; border-radius:5px; overflow:hidden; box-shadow:0 2px 4px rgba(0,0,0,0.2); }
        .flag-white { background:${escapeHtml(generalSettings.flagColor1)}; flex:1; } .flag-blue { background:${escapeHtml(generalSettings.flagColor2)}; flex:1; } .flag-red { background:${escapeHtml(generalSettings.flagColor3)}; flex:1; }
        .search-container { margin:20px 0; display:flex; justify-content:center; }
        .search-box { width:80%; max-width:500px; padding:12px 20px; border:2px solid var(--primary); border-radius:30px; font-size:1rem; outline:none; transition:var(--transition); background-color:var(--card-bg); color:var(--dark); }
        .search-box:focus { box-shadow:0 0 0 3px rgba(90,103,216,0.3); }
        .category-filters { display:flex; flex-wrap:wrap; gap:10px; margin:20px 0; justify-content:center; }
        .category-filter { padding:8px 16px; background:var(--light); border:none; border-radius:20px; cursor:pointer; font-size:0.9rem; transition:var(--transition); color:var(--dark); }
        .category-filter:hover { background:var(--accent); color:white; }
        .category-filter.active { background:var(--primary); color:white; }
        .vocab-container { margin-top:30px; display:grid; grid-template-columns:repeat(auto-fill, minmax(300px, 1fr)); gap:20px; padding:0 10px; }
        .vocab-card { background:var(--card-bg); border-radius:var(--border-radius); box-shadow:var(--shadow); overflow:hidden; transition:var(--transition); position:relative; display:flex; flex-direction:column; }
        .vocab-card:hover { transform:translateY(-5px); box-shadow:var(--hover-shadow); }
        .card-body { padding:20px; flex-grow:1; display:flex; flex-direction:column; justify-content:space-between; }
        .russian-word { font-size:1.8rem; color:var(--russe); margin-bottom:10px; font-weight:700; display:flex; align-items:center; justify-content:space-between; font-family: 'Noto Sans', sans-serif;}
        .russian-word .info-icon { font-size:1rem; color:var(--info-icon-color); cursor:pointer; margin-left:10px; opacity:0.7; transition:opacity 0.2s ease; }
        .russian-word .info-icon:hover { opacity:1; }
        .pronunciation { font-style:italic; color:var(--dark); margin-bottom:15px; font-size:1.1rem; }
        .translation { font-size:1.3rem; color:var(--francais); margin-bottom:20px; font-weight:500; padding-top:10px; border-top:1px solid var(--border-color); }
        .category-tag { background:var(--accent); color:white; padding:3px 8px; border-radius:12px; font-size:0.8rem; display:inline-block; margin-right:5px; margin-bottom:5px; }
        .card-controls { position:absolute; top:10px; right:10px; display:flex; gap:5px; z-index:10; }
        .card-btn { background:var(--light); border:none; border-radius:50%; width:30px; height:30px; display:flex; align-items:center; justify-content:center; cursor:pointer; transition:var(--transition); color:var(--dark); }
        .card-btn:hover { background:var(--accent); color:white; }
        .hidden-translation, .hidden-pronunciation, .hidden-russian { filter:blur(5px); user-select:none; }
        .hidden-translation:hover, .hidden-pronunciation:hover, .hidden-russian:hover { filter:none; }
        .category-heading { margin:30px 0 15px; padding-bottom:10px; border-bottom:2px solid var(--accent); color:var(--primary); font-size:1.8rem; }
        .controls-section { margin:20px 0; display:flex; justify-content:center; gap:15px; flex-wrap:wrap; }
        .control-btn { background:var(--primary); color:white; border:none; padding:10px 20px; border-radius:var(--border-radius); cursor:pointer; font-weight:500; transition:var(--transition); }
        .control-btn:hover { background:var(--accent); }
        .status-section { display:flex; justify-content:center; gap:15px; margin:10px 0; }
        .status-badge { background:var(--card-bg); color:var(--dark); padding:5px 15px; border-radius:20px; font-size:0.9rem; box-shadow:var(--shadow); }
        footer { margin-top:50px; background:var(--primary); color:white; text-align:center; padding:20px; }
        .back-to-top { position:fixed; bottom:20px; right:20px; width:40px; height:40px; background:var(--primary); color:white; border-radius:50%; display:flex; justify-content:center; align-items:center; text-decoration:none; box-shadow:var(--shadow); opacity:0; transition:var(--transition); z-index:100; }
        .back-to-top.visible { opacity:1; }
        .modal-overlay { position:fixed; top:0; left:0; width:100%; height:100%; background:var(--modal-bg); display:flex; justify-content:center; align-items:center; z-index:1000; opacity:0; visibility:hidden; transition:opacity 0.3s ease, visibility 0.3s ease; }
        .modal-overlay.visible { opacity:1; visibility:visible; }
        .modal-content { background:var(--modal-content-bg); padding:30px; border-radius:10px; box-shadow:var(--modal-shadow); max-width:500px; width:90%; text-align:center; position:relative; transform:translateY(-20px); transition:transform 0.3s ease; color:var(--dark); }
        .modal-overlay.visible .modal-content { transform:translateY(0); }
        .modal-close-btn { position:absolute; top:10px; right:10px; background:none; border:none; font-size:1.5rem; cursor:pointer; color:var(--dark); opacity:0.7; transition:opacity 0.2s ease; }
        .modal-close-btn:hover { opacity:1; }
        .modal-title { font-size:1.5rem; color:var(--primary); margin-bottom:15px; }
        .modal-word-pair { font-size:1.1rem; margin-bottom:15px; font-weight:500; }
        .modal-word-pair .russian-modal { color:var(--russe); font-weight:bold; font-family: 'Noto Sans', sans-serif; }
        .modal-word-pair .translation-modal { color:var(--francais); font-style:italic; }
        .modal-nuance-text { font-size:1rem; text-align:left; border-top:1px solid var(--border-color); padding-top:15px; margin-top:15px; }
        @media (max-width:768px) { .vocab-container{grid-template-columns:1fr;} .category-filters{justify-content:center;} .category-filter{margin:3px;} .controls-section{flex-direction:column;align-items:center;} .control-btn{width:90%;} .nav-buttons{flex-direction:column;align-items:center;} .nav-btn{width:90%;text-align:center;margin:2px 0;} }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <button class="theme-toggle" id="theme-toggle">🌙</button>
            <h1>${escapeHtml(vocabularySettings.pageTitle)}</h1>
            <p>${escapeHtml(vocabularySettings.pageSubtitle)}</p>
            <div class="flag-colors"> <div class="flag-white"></div> <div class="flag-blue"></div> <div class="flag-red"></div> </div>
        </div>
    </header>
    <nav class="navigation">
        <div class="container">
            <div class="nav-buttons">
                <a href="index.html" class="nav-btn">🏠 Accueil</a>
                <a href="alphabet_${slug}.html" class="nav-btn">🔤 Alphabet</a>
                <a href="vocabulaire_${slug}.html" class="nav-btn active">📚 Vocabulaire</a>
                <a href="cours-21-jours_${slug}.html" class="nav-btn">📅 Programme 21 jours</a>
            </div>
        </div>
    </nav>
    <main>
        <div class="container">
            <div class="search-container">
                <input type="text" class="search-box" id="vocab-search" placeholder="${escapeHtml(vocabularySettings.searchPlaceholder)}">
            </div>
            <div class="controls-section">
                <button class="control-btn" id="hide-all-russian">Masquer mots (${escapeHtml(generalSettings.targetLanguage)})</button>
                <button class="control-btn" id="show-all-russian">Afficher mots (${escapeHtml(generalSettings.targetLanguage)})</button>
                <button class="control-btn" id="hide-all-pronunciations">Masquer prononciations</button>
                <button class="control-btn" id="show-all-pronunciations">Afficher prononciations</button>
                <button class="control-btn" id="hide-all-translations">Masquer traductions</button>
                <button class="control-btn" id="show-all-translations">Afficher traductions</button>
                <button class="control-btn" id="restore-all-words">Restaurer tous les mots</button>
            </div>
            <div class="status-section">
                <div class="status-badge">Mots masqués: <span id="hidden-words-count">0</span></div>
                <div class="status-badge">Mots affichés: <span id="visible-words-count">0</span></div>
            </div>
            <div class="category-filters">${categoryFiltersHTML}</div>
            <h2 class="category-heading" id="current-category">Tous les mots</h2>
            <div class="vocab-container" id="vocab-container"></div>
        </div>
    </main>
    <a href="#" class="back-to-top" id="back-to-top">↑</a>
    <footer> <p>${escapeHtml(vocabularySettings.pageTitle)} - Apprentissage du vocabulaire</p> </footer>
    <div id="nuanceModal" class="modal-overlay">
        <div class="modal-content">
            <button class="modal-close-btn" id="closeModalBtn">✖</button>
            <h3 class="modal-title">Nuance de sens</h3>
            <div class="modal-word-pair">
                <span class="russian-modal" id="modalRussianWord"></span> - 
                <span class="translation-modal" id="modalTranslation"></span>
            </div>
            <p class="modal-nuance-text" id="modalNuanceText"></p>
        </div>
    </div>
    <script>
        const vocabulary = ${JSON.stringify(vocabularyArray, null, 2)};
        let currentCategory = "all";
        let allTranslationsHidden = false, allPronunciationsHidden = false, allRussianHidden = false;
        let hiddenWords = new Set();

        function initializeApp() { updateVocabularyDisplay(); setupEventListeners(); updateWordCounters(); loadTheme(); }
        function setupEventListeners() {
            document.querySelectorAll('.category-filter').forEach(filter => {
                filter.addEventListener('click', function() {
                    document.querySelectorAll('.category-filter').forEach(f => f.classList.remove('active'));
                    this.classList.add('active');
                    currentCategory = this.getAttribute('data-category');
                    document.getElementById('current-category').textContent = this.textContent === 'Tous' ? 'Tous les mots' : this.textContent;
                    updateVocabularyDisplay();
                });
            });
            document.getElementById('vocab-search').addEventListener('input', updateVocabularyDisplay);
            window.addEventListener('scroll', () => {
                document.getElementById('back-to-top').classList.toggle('visible', (document.body.scrollTop > 200 || document.documentElement.scrollTop > 200));
            });
            document.getElementById('back-to-top').addEventListener('click', e => { e.preventDefault(); window.scrollTo({top:0, behavior:'smooth'}); });
            
            const themeToggleBtn = document.getElementById('theme-toggle');
            if (themeToggleBtn) {
                 themeToggleBtn.addEventListener('click', () => {
                    document.body.classList.toggle('dark-mode');
                    let theme = 'light-mode';
                    if (document.body.classList.contains('dark-mode')) {
                        theme = 'dark-mode';
                        themeToggleBtn.textContent = '☀️';
                    } else {
                        themeToggleBtn.textContent = '🌙';
                    }
                    localStorage.setItem('theme-${slug}', theme);
                });
            }

            ['hide-all-translations', 'show-all-translations', 'hide-all-pronunciations', 'show-all-pronunciations', 'hide-all-russian', 'show-all-russian'].forEach(id => {
                document.getElementById(id)?.addEventListener('click', function() {
                    const action = this.id.split('-')[0]; // hide or show
                    const type = this.id.split('-')[2]; // translations, pronunciations, russian
                    const elementsClass = type === 'russian' ? '.russian-word' : '.' + type.slice(0, -1); // .translation, .pronunciation
                    const hiddenClass = 'hidden-' + type.slice(0, -1); // hidden-translation, hidden-pronunciation, hidden-russian
                    
                    document.querySelectorAll(elementsClass).forEach(el => {
                        if (action === 'hide') el.classList.add(hiddenClass);
                        else el.classList.remove(hiddenClass);
                    });
                    if (type === 'translations') allTranslationsHidden = (action === 'hide');
                    if (type === 'pronunciations') allPronunciationsHidden = (action === 'hide');
                    if (type === 'russian') allRussianHidden = (action === 'hide');
                });
            });
             document.getElementById('restore-all-words').addEventListener('click', () => { hiddenWords.clear(); updateVocabularyDisplay(); updateWordCounters(); });
             document.getElementById('closeModalBtn').addEventListener('click', closeModal);
             document.getElementById('nuanceModal').addEventListener('click', function(e){ if(e.target === this) closeModal(); });
        }
        function updateVocabularyDisplay() {
            const searchTerm = document.getElementById('vocab-search').value.toLowerCase();
            const filtered = vocabulary.filter(word => {
                const matchesCategory = currentCategory === 'all' || word.categories.includes(currentCategory);
                const matchesSearch = word.russian.toLowerCase().includes(searchTerm) || word.pronunciation.toLowerCase().includes(searchTerm) || word.translation.toLowerCase().includes(searchTerm);
                return matchesCategory && matchesSearch && !hiddenWords.has(word.russian);
            });
            const container = document.getElementById('vocab-container');
            container.innerHTML = '';
            filtered.forEach(word => {
                const card = document.createElement('div');
                card.className = 'vocab-card';
                card.dataset.word = word.russian;
                card.dataset.categories = word.categories.join(',');
                const infoBtnHtml = word.nuance ? \`<button class="card-btn info-icon-btn" title="Plus d'informations">ℹ️</button>\` : '';
                card.innerHTML = \`
                    <div class="card-controls"> \${infoBtnHtml}
                        <button class="card-btn toggle-russian-btn" title="Masquer/Afficher le mot">🆎</button>
                        <button class="card-btn toggle-pronunciation-btn" title="Masquer/Afficher la prononciation">🔊</button>
                        <button class="card-btn toggle-translation-btn" title="Masquer/Afficher la traduction">👁️</button>
                        <button class="card-btn remove-word-btn" title="Masquer ce mot">❌</button>
                    </div>
                    <div class="card-body">
                        <div class="russian-word \${allRussianHidden ? 'hidden-russian':''}"><span class="text-content">\${word.russian}</span></div>
                        <div class="pronunciation \${allPronunciationsHidden ? 'hidden-pronunciation':''}"><span class="text-content">\${word.pronunciation}</span></div>
                        <div class="translation \${allTranslationsHidden ? 'hidden-translation':''}"><span class="text-content">\${word.translation}</span></div>
                        <div style="display:flex;flex-wrap:wrap;gap:5px;margin-bottom:10px;">\${word.categories.map(cat => \`<span class="category-tag">\${cat}</span>\`).join('')}</div>
                    </div>\`;
                container.appendChild(card);
                card.querySelector('.toggle-russian-btn').addEventListener('click', function(){ this.closest('.vocab-card').querySelector('.russian-word').classList.toggle('hidden-russian'); });
                card.querySelector('.toggle-pronunciation-btn').addEventListener('click', function(){ this.closest('.vocab-card').querySelector('.pronunciation').classList.toggle('hidden-pronunciation'); });
                card.querySelector('.toggle-translation-btn').addEventListener('click', function(){ this.closest('.vocab-card').querySelector('.translation').classList.toggle('hidden-translation'); });
                card.querySelector('.remove-word-btn').addEventListener('click', function(){ hiddenWords.add(this.closest('.vocab-card').dataset.word); this.closest('.vocab-card').remove(); updateWordCounters(); });
                if(word.nuance) card.querySelector('.info-icon-btn').addEventListener('click', () => openModal(word.russian, word.translation, word.nuance));
            });
            const currentCatName = document.querySelector(\`.category-filter[data-category="\${currentCategory}"]\`).textContent;
            document.getElementById('current-category').textContent = \`\${currentCatName} (\${filtered.length})\`;
            updateWordCounters();
        }
        function updateWordCounters() {
            const totalWords = vocabulary.length;
            const visibleWordsCount = document.querySelectorAll('#vocab-container .vocab-card').length;
            document.getElementById('hidden-words-count').textContent = totalWords - visibleWordsCount;
            document.getElementById('visible-words-count').textContent = visibleWordsCount;
        }
         function loadTheme() {
            const themeToggleBtn = document.getElementById('theme-toggle');
            const currentTheme = localStorage.getItem('theme-${slug}');
            if (currentTheme) {
                document.body.classList.add(currentTheme);
                if (themeToggleBtn) themeToggleBtn.textContent = currentTheme === 'dark-mode' ? '☀️' : '🌙';
            } else {
                 if (themeToggleBtn) themeToggleBtn.textContent = '🌙';
            }
        }
        function openModal(russianWord, translation, nuanceText) {
            document.getElementById('modalRussianWord').textContent = russianWord;
            document.getElementById('modalTranslation').textContent = translation;
            document.getElementById('modalNuanceText').innerHTML = nuanceText.replace(/\\n/g, '<br>');
            document.getElementById('nuanceModal').classList.add('visible');
        }
        function closeModal() { document.getElementById('nuanceModal').classList.remove('visible'); }
        document.addEventListener('DOMContentLoaded', initializeApp);
    </script>
</body>
</html>`;
    downloadFile(`vocabulaire_${slug}.html`, html);
  };
  
  const generateCourseHTML = () => {
    const slug = generateSlug(generalSettings.targetLanguage);
    
    // Parse weeksData
    const weeks = courseSettings.weeksData.split('\n').filter(line => line.trim()).map((line, index) => {
        const parts = line.split(';');
        return { id: `week${index + 1}`, title: parts[0]?.trim() || `Semaine ${index + 1}`, objective: parts[1]?.trim() || 'Objectif de la semaine.' };
    });

    let weeksConfigJs = `const weeksConfig = {`;
    weeks.forEach(week => {
        weeksConfigJs += `\n    '${week.id}': { startDay: ${(parseInt(week.id.replace('week',''))-1)*7 + 1}, endDay: ${parseInt(week.id.replace('week',''))*7}, title: "${escapeHtml(week.title)}" },`;
    });
    weeksConfigJs += `\n};`;


    // Parse daysData
    const daysRaw = courseSettings.daysData.split('__DAY_SEPARATOR__').map(d => d.trim()).filter(d => d);
    let dayContentsHTML = '';
    const allDaysData = [];

    daysRaw.forEach(dayBlock => {
        const lines = dayBlock.split('\n').map(l => l.trim());
        const headerLine = lines.shift(); // First line is DayNumber;Title;Objective
        if (!headerLine) return;

        const [dayNumStr, dayTitle, dayObjective] = headerLine.split(';');
        const dayNum = parseInt(dayNumStr);
        if (isNaN(dayNum)) return;

        allDaysData.push({dayNum, title: dayTitle, objective: dayObjective});

        let dayHTML = `<div id="jour${dayNum}" class="tab-content"><div class="card"><div class="card-header"><h2>${escapeHtml(dayTitle)}</h2></div><div class="card-body">`;
        dayHTML += `<div class="section"><h3 class="section-title">Objectif du jour</h3><p>${escapeHtml(dayObjective)}</p></div>`;

        lines.forEach(sectionLine => {
            const [typeAndMaybeTitle, ...dataParts] = sectionLine.split('|');
            const [type, ...titleParts] = typeAndMaybeTitle.split(':');
            const sectionTitle = titleParts.join(':').trim();
            const contentData = dataParts.join('|').trim();

            dayHTML += `<div class="section">`;
            if (sectionTitle) dayHTML += `<h3 class="section-title">${escapeHtml(sectionTitle)}</h3>`;

            switch (type.trim().toUpperCase()) {
                case 'TEXT_SECTION':
                    dayHTML += `<p>${escapeHtml(contentData).replace(/\n/g, '<br>')}</p>`;
                    break;
                case 'LETTER_GRID':
                    const letters = contentData.split('|').map(l => l.split(','));
                    dayHTML += `<div class="letter-grid">`;
                    letters.forEach(l => {
                        if(l.length >= 3) dayHTML += `<div class="letter-item"><div class="cyrillic"><span>${escapeHtml(l[0])}</span><span>${escapeHtml(l[1] || l[0])}</span></div><div class="pronunciation">${escapeHtml(l[2])}</div>${l[3] ? `<div class="example">${escapeHtml(l[3])}</div>` : ''}</div>`;
                    });
                    dayHTML += `</div>`;
                    break;
                case 'VOCAB_LIST':
                     const vocabItems = contentData.split('|').map(v => v.split(','));
                     dayHTML += `<div class="vocab-list">`;
                     vocabItems.forEach(v => {
                         if(v.length >= 3) dayHTML += `<div class="vocab-item"><div><div class="term">${escapeHtml(v[0])}</div><div class="pronunciation">${escapeHtml(v[1])}</div></div><div class="translation">${escapeHtml(v[2])}</div></div>`;
                     });
                     dayHTML += `</div>`;
                    break;
                case 'NOTE_BOX':
                case 'FOCUS_BOX':
                     dayHTML += `<div class="note-box">${sectionTitle ? `<div class="note-title">${escapeHtml(sectionTitle)}</div>` : ''}<p>${escapeHtml(contentData).replace(/\n/g, '<br>')}</p></div>`;
                    break;
                case 'EXERCISE':
                     dayHTML += `<div class="exercise">${sectionTitle ? `<div class="exercise-title">${escapeHtml(sectionTitle)}</div>` : ''}<p>${escapeHtml(contentData).replace(/\n/g, '<br>')}</p></div>`;
                    break;
                case 'DIALOGUE':
                    const dialogueLines = contentData.split('|');
                    dayHTML += `<div class="dialogue-box">`;
                    dialogueLines.forEach(line => {
                        const [speakerAndRussian, translation] = line.split(':', 2);
                        const [speaker, russianText] = speakerAndRussian.split(':',2); // In case speaker name has a colon
                        if (speaker && russianText && translation) {
                             dayHTML += `<div class="dialogue-line"><span class="speaker">${escapeHtml(speaker.trim())}:</span> <span class="russian">${escapeHtml(russianText.trim())}</span><span class="translation">${escapeHtml(translation.trim())}</span></div>`;
                        } else if (speaker && russianText) { // No translation provided
                             dayHTML += `<div class="dialogue-line"><span class="speaker">${escapeHtml(speaker.trim())}:</span> <span class="russian">${escapeHtml(russianText.trim())}</span></div>`;
                        }

                    });
                    dayHTML += `</div>`;
                    break;
                case 'RECAP_LIST':
                    const recapItems = contentData.split('|');
                    dayHTML += `<div class="recap-list">${sectionTitle ? `<h4>${escapeHtml(sectionTitle)}</h4>` : ''}<ul>`;
                    recapItems.forEach(item => dayHTML += `<li>${escapeHtml(item)}</li>`);
                    dayHTML += `</ul></div>`;
                    break;
                default:
                    dayHTML += `<p>Type de section inconnu: ${escapeHtml(type)}</p><p>${escapeHtml(contentData)}</p>`;
            }
            dayHTML += `</div>`; // Close section
        });

        dayHTML += `</div></div>`; // Close card-body and card
        dayHTML += `<div class="day-navigator">
                        <button class="nav-button" id="prevDayBtn${dayNum}" onclick="previousDay()">← Jour précédent</button>
                        <button class="nav-button" id="nextDayBtn${dayNum}" onclick="nextDay()">${dayNum === 21 ? 'Valider programme' : 'Jour suivant →'}</button>
                    </div></div>`; // Close tab-content
        dayContentsHTML += dayHTML;
    });
    
    let weekSummariesHTML = '';
    let sidebarWeeksHTML = '';
    weeks.forEach((week, index) => {
        weekSummariesHTML += `
            <div id="weekSummary${index+1}" class="week-summary-content">
                <div class="card">
                    <div class="card-header"><h2>${escapeHtml(week.title)}</h2></div>
                    <div class="card-body">
                        <div class="section"><h3 class="section-title">Objectif de la semaine</h3><p>${escapeHtml(week.objective)}</p></div>
                        <div class="section"><h3 class="section-title">Parcourir les jours</h3><div class="day-buttons-summary" id="dayButtonsWeek${index+1}"></div></div>
                    </div>
                </div>
            </div>`;
        sidebarWeeksHTML += `
            <li class="sidebar-week-item">
                <button class="sidebar-week-btn" data-week="week${index+1}">${escapeHtml(week.title)}</button>
                <ul class="sidebar-day-list" id="sidebar-day-list-week${index+1}"></ul>
            </li>`;
    });


    const html = `
<!DOCTYPE html>
<html lang="${generalSettings.nativeLanguage.slice(0,2).toLowerCase()}">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>${escapeHtml(courseSettings.pageTitle)} - ${escapeHtml(generalSettings.languageName)}</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Noto+Sans:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: ${escapeHtml(generalSettings.themePrimary)}; --secondary: ${escapeHtml(generalSettings.themeSecondary)}; --accent: ${escapeHtml(generalSettings.themeAccent)};
            --light: ${escapeHtml(generalSettings.themeLight)}; --dark: ${escapeHtml(generalSettings.themeDark)};
            --russe: ${escapeHtml(generalSettings.themeRusse)}; --francais: ${escapeHtml(generalSettings.themeFrancais)};
            --bg-primary: ${escapeHtml(generalSettings.themeBackground)}; --bg-secondary: ${escapeHtml(generalSettings.themeLight)};
            --text-primary: ${escapeHtml(generalSettings.themeDark)}; --text-secondary: #718096;
            --border-color: #e2e8f0; --card-bg: ${escapeHtml(generalSettings.themeCardBg)};
            --success: #38a169; --warning: #d69e2e; --info: #3182ce;
            --header-shadow: 0 4px 6px rgba(0,0,0,0.1); --card-hover-shadow: 0 8px 15px rgba(0,0,0,0.2);
            --sidebar-bg: #f0f5ff; --sidebar-shadow: 2px 0 5px rgba(0,0,0,0.1);
            --sidebar-active-bg: var(--primary); --sidebar-hover-bg: #e2e8f0;
        }
        body.dark-mode {
            --primary: #3b82f6; --secondary: #ef4444; --accent: #818cf8;
            --light: #1f2937; --dark: #f9fafb; --russe: #f87171; --francais: #60a5fa;
            --bg-primary: #111827; --bg-secondary: #1e293b;
            --text-primary: #f9fafb; --text-secondary: #d1d5db;
            --border-color: #374151; --card-bg: #1e293b;
            --sidebar-bg: #1e293b; --sidebar-shadow: 2px 0 5px rgba(0,0,0,0.3);
            --sidebar-active-bg: var(--primary); --sidebar-hover-bg: #374151;
        }
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body { font-family: 'Inter', sans-serif; line-height: 1.6; color: var(--text-primary); background: var(--bg-primary); transition: background 0.3s, color 0.3s; }
        .container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }
        header { background: linear-gradient(135deg, var(--primary), var(--accent)); color: white; padding: 30px 0; text-align: center; box-shadow: var(--header-shadow); position:relative; }
        header h1 { font-size: 2.5rem; margin-bottom: 15px; }
        .theme-toggle { position: absolute; right: 20px; top: 20px; background: transparent; border: none; color: white; font-size: 1.5rem; cursor: pointer; z-index: 1001; }
        .flag-colors { display: flex; height: 10px; margin: 20px auto 0; width: 200px; border-radius: 5px; overflow: hidden; box-shadow: 0 2px 4px rgba(0,0,0,0.2); }
        .flag-white { background: ${escapeHtml(generalSettings.flagColor1)}; flex: 1; } .flag-blue { background: ${escapeHtml(generalSettings.flagColor2)}; flex: 1; } .flag-red { background: ${escapeHtml(generalSettings.flagColor3)}; flex: 1; }
        .navigation { background: var(--card-bg); padding: 15px 0; box-shadow: 0 2px 4px rgba(0,0,0,0.1); margin-bottom: 30px; }
        .nav-buttons { display: flex; justify-content: center; gap: 15px; flex-wrap: wrap; }
        .nav-btn { background: var(--primary); color: white; padding: 10px 20px; text-decoration: none; border-radius: 6px; font-weight: 500; transition: all 0.3s ease; font-size: 0.9rem; }
        .nav-btn:hover { background: var(--accent); transform: translateY(-2px); }
        .nav-btn.active { background: var(--secondary); }
        .content-wrapper { display: flex; flex-direction: row; }
        .sidebar-nav { width: 250px; background-color: var(--sidebar-bg); box-shadow: var(--sidebar-shadow); padding: 20px 0; flex-shrink: 0; border-radius: 0 10px 10px 0; position: sticky; top: 20px; align-self: flex-start; height: calc(100vh - 40px); overflow-y: auto; margin-right:20px;}
        .sidebar-nav h3 { color: var(--primary); text-align: center; margin-bottom: 20px; font-size: 1.3rem; padding: 0 15px; }
        .sidebar-week-list, .sidebar-day-list { list-style: none; padding: 0; margin: 0; }
        .sidebar-week-btn, .sidebar-day-btn { display: block; width: 100%; padding: 12px 20px; text-align: left; background: transparent; border: none; cursor: pointer; font-size: 1rem; color: var(--text-primary); transition: all 0.3s ease; border-radius: 5px; font-weight: 500; }
        .sidebar-week-btn:hover, .sidebar-day-btn:hover { background-color: var(--sidebar-hover-bg); color: var(--primary); }
        .sidebar-week-btn.active-week, .sidebar-day-btn.active-day { background-color: var(--sidebar-active-bg); color: white; font-weight: 600; }
        .sidebar-day-list { padding-left: 20px; border-left: 2px solid var(--border-color); margin-left: 10px; margin-top: 5px; max-height: 0; overflow: hidden; transition: max-height 0.3s ease-out; }
        .sidebar-day-list.active { max-height: 500px; /* Adjust as needed */ }
        .main-content { flex-grow: 1; padding: 0px 0px 0px 0px; /* Removed left padding, adjust right padding if needed */ }
        .progress-container { background: var(--card-bg); padding: 20px; margin-bottom: 20px; border-radius: 10px; box-shadow: var(--header-shadow); }
        .progress-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; }
        .progress-bar { width: 100%; height: 20px; background: var(--border-color); border-radius: 10px; overflow: hidden; }
        .progress-fill { height: 100%; background: linear-gradient(90deg, var(--success), var(--accent)); transition: width 0.5s ease; display: flex; align-items: center; justify-content: center; color: white; font-size: 0.9rem; font-weight: 500; }
        .week-summary-content, .tab-content { display: none; }
        .week-summary-content.active, .tab-content.active { display: block; animation: fadeIn 0.5s ease; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        .card { background: var(--card-bg); border-radius: 12px; box-shadow: var(--header-shadow); margin-bottom: 30px; overflow: hidden; }
        .card-header { padding: 20px; background: var(--primary); color: white; } .card-header h2 { font-size: 1.5rem; }
        .card-body { padding: 25px; } .section { margin-bottom: 25px; } .section-title { font-size: 1.25rem; color: var(--primary); margin-bottom: 15px; padding-bottom: 8px; border-bottom: 2px solid var(--accent); }
        .vocab-list, .letter-grid, .numbers-grid { display: grid; gap: 15px; margin-top: 15px; }
        .vocab-list { grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); }
        .letter-grid { grid-template-columns: repeat(auto-fill, minmax(160px, 1fr)); }
        .numbers-grid { grid-template-columns: repeat(auto-fill, minmax(120px, 1fr)); }
        .vocab-item, .letter-item, .number-item { background: var(--bg-secondary); padding: 15px; border-radius: 8px; border-left: 4px solid var(--accent); transition: all 0.2s; }
        .vocab-item:hover, .letter-item:hover, .number-item:hover { background: #e9ecef; transform: translateY(-2px); } /* Consider dark mode hover */
        .term, .cyrillic span, .digit { font-weight: bold; } .term, .cyrillic span {color: var(--russe); font-family: 'Noto Sans', sans-serif;} .digit {color: var(--primary);}
        .cyrillic { font-size: 2rem; display:flex; justify-content:center; }
        .pronunciation { color: var(--text-secondary); font-style: italic; }
        .translation, .example, .russian { color: var(--francais); }
        .note-box, .exercise, .dialogue-box, .recap-list { padding: 15px; border-radius: 8px; margin-top: 15px; }
        .note-box { background: #e6fffa; border-left: 4px solid var(--info); } .note-title { font-weight: bold; color: var(--info); }
        .exercise { background: #f0f4f8; border-left: 4px solid var(--warning); } .exercise-title { font-weight: bold; color: var(--warning); }
        .dialogue-box { background: #f8f9fa; border: 1px solid var(--border-color); } .speaker { font-weight: bold; color: var(--primary); } .russian {color: var(--russe); font-family: 'Noto Sans', sans-serif;}
        .recap-list { background: #f0f4ff; border-left: 4px solid var(--success); } .recap-list ul { margin-left: 20px; }
        .day-navigator { display: flex; justify-content: space-between; margin: 20px 0; }
        .nav-button { padding: 10px 20px; background: var(--primary); color: white; border: none; border-radius: 5px; cursor: pointer; font-weight: 500; transition: background 0.2s, transform 0.1s; }
        .nav-button:hover { background: var(--accent); transform: translateY(-2px); } .nav-button:disabled { background: #cbd5e0; cursor: not-allowed; }
        .nav-button.validate { background: var(--success); } .nav-button.validate:hover { background: #2f855a; }
        .congratulations-message { background: #d4f1d4; border-left: 8px solid var(--success); padding: 30px; border-radius: 12px; margin: 40px 0; text-align: center; animation: bounceIn 0.8s ease-out; }
        .congratulations-message h3 { color: var(--success); font-size: 2rem; }
        @keyframes bounceIn { 0%{transform:scale(0.8);opacity:0;} 50%{transform:scale(1.05);opacity:1;} 70%{transform:scale(0.95);} 100%{transform:scale(1);opacity:1;} }
        .back-to-top { position: fixed; bottom: 20px; right: 20px; width: 50px; height: 50px; background: var(--primary); color: white; border-radius: 50%; display: flex; justify-content: center; align-items: center; text-decoration: none; opacity: 0; transition: opacity 0.3s; z-index: 1000; font-size:1.5rem; }
        .back-to-top.visible { opacity: 1; }
        footer { background: var(--primary); color: white; text-align: center; padding: 30px 0; margin-top: 50px; }
        @media (max-width: 768px) { 
            .nav-buttons { flex-direction: column; align-items: center; } .nav-btn { width: 80%; text-align: center; } 
            .content-wrapper { flex-direction: column; }
            .sidebar-nav { position: static; width: 100%; margin-bottom: 20px; height:auto; border-radius:10px; }
            .main-content { margin-left:0; padding: 0 10px; }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <button id="theme-toggle" class="theme-toggle">🌙</button>
            <h1>${escapeHtml(generalSettings.languageName)}</h1>
            <p>Votre guide complet pour maîtriser la langue ${escapeHtml(generalSettings.targetLanguage.toLowerCase())}</p>
            <div class="flag-colors"> <div class="flag-white"></div> <div class="flag-blue"></div> <div class="flag-red"></div> </div>
        </div>
    </header>
    <nav class="navigation">
        <div class="container">
            <div class="nav-buttons">
                <a href="index.html" class="nav-btn">🏠 Accueil</a>
                <a href="alphabet_${slug}.html" class="nav-btn">🔤 Alphabet</a>
                <a href="vocabulaire_${slug}.html" class="nav-btn">📚 Vocabulaire</a>
                <a href="cours-21-jours_${slug}.html" class="nav-btn active">📅 Programme 21 jours</a>
            </div>
        </div>
    </nav>
    <div class="container content-wrapper">
        <nav class="sidebar-nav">
            <h3>Programme 21 Jours</h3>
            <ul class="sidebar-week-list">${sidebarWeeksHTML}</ul>
        </nav>
        <main class="main-content">
            <div class="progress-container">
                <div class="progress-header">
                    <h3>Votre progression</h3>
                    <span id="progress-text">0/21 ${escapeHtml(courseSettings.progressText)}</span>
                </div>
                <div class="progress-bar">
                    <div class="progress-fill" id="progress-fill" style="width: 0%">0%</div>
                </div>
            </div>
            ${weekSummariesHTML}
            ${weeks.map(week => `<div id="${week.id}" class="week-content"></div>`).join('')}
            <!-- Daily content will be loaded here by JS -->
            <div id="daily-content-area">
                ${dayContentsHTML}
            </div>
             <div class="congratulations-message" id="congratulations-message" style="display: none;">
                <h3>${escapeHtml(courseSettings.congratsTitle)}</h3>
                <p>${escapeHtml(courseSettings.congratsMessage)}</p>
                <ul>${courseSettings.congratsAchievements.split('\n').map(ach => `<li>${escapeHtml(ach)}</li>`).join('')}</ul>
            </div>
        </main>
    </div>
    <a href="#" class="back-to-top" id="back-to-top">↑</a>
    <footer> <p>&copy; ${new Date().getFullYear()} ${escapeHtml(generalSettings.languageName)}</p> </footer>
    <script>
        ${weeksConfigJs}
        let userProgress = { currentDay: 1, completedDays: [], totalProgress: 0, lastVisit: new Date().toISOString() };
        let activeWeekId = '';

        function loadProgress() {
            const saved = localStorage.getItem('courseProgress-${slug}');
            if (saved) {
                userProgress = JSON.parse(saved);
                if (userProgress.currentDay > 21) userProgress.currentDay = 21;
            }
            updateProgressUI();
        }
        function saveProgress() {
            userProgress.lastVisit = new Date().toISOString();
            localStorage.setItem('courseProgress-${slug}', JSON.stringify(userProgress));
            updateProgressUI();
        }
        function updateProgressUI() {
            const fill = document.getElementById('progress-fill');
            const text = document.getElementById('progress-text');
            userProgress.totalProgress = Math.round((userProgress.completedDays.length / 21) * 100);
            if(fill) fill.style.width = userProgress.totalProgress + '%';
            if(fill) fill.textContent = userProgress.totalProgress + '%';
            if(text) text.textContent = userProgress.completedDays.length + '/21 ${escapeHtml(courseSettings.progressText)}';
        }
        function markDayComplete(day) {
            if (!userProgress.completedDays.includes(day)) {
                userProgress.completedDays.push(day);
                saveProgress();
            }
        }
        
        function updateActiveNavigationColors() {
            document.querySelectorAll('.navigation .nav-btn').forEach(item => {
                item.classList.remove('active');
                if (item.href && item.href.includes('cours-21-jours_${slug}.html')) item.classList.add('active');
            });
            document.querySelectorAll('.sidebar-week-btn').forEach(btn => btn.classList.remove('active-week'));
            const currentSidebarWeekBtn = document.querySelector(\`.sidebar-week-btn[data-week="\${activeWeekId}"]\`);
            if (currentSidebarWeekBtn) currentSidebarWeekBtn.classList.add('active-week');

            document.querySelectorAll('.sidebar-day-list .sidebar-day-btn, .day-buttons-summary .nav-button').forEach(btn => btn.classList.remove('active-day'));
            const currentDayBtnInSidebar = document.querySelector(\`.sidebar-day-list .sidebar-day-btn[data-day="\${userProgress.currentDay}"]\`);
            if (currentDayBtnInSidebar) currentDayBtnInSidebar.classList.add('active-day');
            const currentDayBtnInSummary = document.querySelector(\`.day-buttons-summary .nav-button[data-day="\${userProgress.currentDay}"]\`);
            if (currentDayBtnInSummary) currentDayBtnInSummary.classList.add('active-day');
        }

        function openWeek(weekName, activateSpecificDay = null) {
            activeWeekId = weekName;
            document.querySelectorAll('.week-content, .week-summary-content, .tab-content').forEach(el => el.classList.remove('active'));
            document.querySelectorAll('.sidebar-week-btn').forEach(btn => btn.classList.remove('active-week'));
            document.querySelectorAll('.sidebar-day-list').forEach(list => list.classList.remove('active'));

            const currentSidebarWeekBtn = document.querySelector(\`.sidebar-week-btn[data-week="\${weekName}"]\`);
            if (currentSidebarWeekBtn) currentSidebarWeekBtn.classList.add('active-week');
            
            generateSidebarDayTabs(weekName);
            const dayListForWeek = document.getElementById(\`sidebar-day-list-\${weekName}\`);
            if(dayListForWeek) dayListForWeek.classList.add('active');
            
            generateDayButtonsForSummary(weekName);

            if (activateSpecificDay !== null) {
                userProgress.currentDay = activateSpecificDay;
                const weekContentEl = document.getElementById(weekName);
                if(weekContentEl) weekContentEl.classList.add('active'); // Show the main week container if needed
                openTab(\`jour\${activateSpecificDay}\`);
            } else {
                const summaryEl = document.getElementById(\`weekSummary\${weekName.replace('week', '')}\`);
                if(summaryEl) summaryEl.classList.add('active');
            }
            updateActiveNavigationColors();
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function openTab(tabName) {
            document.querySelectorAll('.week-summary-content, .tab-content').forEach(el => el.classList.remove('active'));
            
            const dayNumber = parseInt(tabName.replace('jour', ''));
            const weekNumber = Math.ceil(dayNumber / 7);
            const weekId = \`week\${weekNumber}\`;

            const weekContentEl = document.getElementById(weekId);
            // if(weekContentEl) weekContentEl.classList.add('active'); // Ensure parent week container is active. Handled by openWeek.

            const dayContentEl = document.getElementById(tabName);
            if(dayContentEl) dayContentEl.classList.add('active');
            
            userProgress.currentDay = dayNumber;
            saveProgress();

            if (activeWeekId !== weekId) {
                activeWeekId = weekId;
                document.querySelectorAll('.sidebar-week-btn').forEach(btn => btn.classList.remove('active-week'));
                const currentSidebarWeekBtn = document.querySelector(\`.sidebar-week-btn[data-week="\${weekId}"]\`);
                if (currentSidebarWeekBtn) currentSidebarWeekBtn.classList.add('active-week');
                
                document.querySelectorAll('.sidebar-day-list').forEach(list => list.classList.remove('active'));
                generateSidebarDayTabs(weekId); // Regenerate if changing week
                const dayListForWeek = document.getElementById(\`sidebar-day-list-\${weekId}\`);
                if(dayListForWeek) dayListForWeek.classList.add('active');
            }
            updateActiveNavigationColors();
            updateDayNavigatorButtons(dayNumber);
            const congratsMsg = document.getElementById('congratulations-message');
            if(congratsMsg) congratsMsg.style.display = 'none';
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function nextDay() {
            const currentDay = userProgress.currentDay;
            markDayComplete(currentDay);
            if (currentDay < 21) {
                openTab(\`jour\${currentDay + 1}\`);
            } else if (currentDay === 21) {
                validateProgram();
            }
        }
        function previousDay() {
            if (userProgress.currentDay > 1) {
                openTab(\`jour\${userProgress.currentDay - 1}\`);
            }
        }
        function updateDayNavigatorButtons(currentDay) {
            document.querySelectorAll('.day-navigator').forEach(nav => {
                const prevBtn = nav.querySelector(\`#prevDayBtn\${currentDay}\`);
                const nextBtn = nav.querySelector(\`#nextDayBtn\${currentDay}\`);
                if (prevBtn) prevBtn.disabled = (currentDay === 1);
                if (nextBtn) {
                    if (currentDay === 21) {
                        nextBtn.textContent = '${escapeHtml(courseSettings.congratsTitle)}'; // Or "Valider Programme"
                        nextBtn.classList.add('validate');
                        nextBtn.onclick = validateProgram;
                    } else {
                        nextBtn.textContent = 'Jour suivant →';
                        nextBtn.classList.remove('validate');
                        nextBtn.onclick = nextDay;
                    }
                }
            });
        }
        function validateProgram() {
            markDayComplete(21);
            const congratsMsg = document.getElementById('congratulations-message');
            if(congratsMsg) {
                congratsMsg.style.display = 'block';
                window.scrollTo({ top: document.body.scrollHeight, behavior: 'smooth' });
            }
        }
        function generateSidebarDayTabs(weekName) {
            const sidebarDayList = document.getElementById(\`sidebar-day-list-\${weekName}\`);
            if (!sidebarDayList) return;
            sidebarDayList.innerHTML = '';
            const config = weeksConfig[weekName];
            if (!config) return;
            for (let i = config.startDay; i <= config.endDay; i++) {
                const listItem = document.createElement('li');
                listItem.className = 'sidebar-day-item';
                const button = document.createElement('button');
                button.className = 'sidebar-day-btn';
                button.dataset.day = i;
                button.textContent = \`Jour \${i}\`;
                button.onclick = () => openTab(\`jour\${i}\`);
                listItem.appendChild(button);
                sidebarDayList.appendChild(listItem);
            }
        }
        function generateDayButtonsForSummary(weekName) {
            const dayButtonsContainer = document.getElementById(\`dayButtonsWeek\${weekName.replace('week','')}\`);
            if (!dayButtonsContainer) return;
            dayButtonsContainer.innerHTML = '';
            const config = weeksConfig[weekName];
            if (!config) return;
            for (let i = config.startDay; i <= config.endDay; i++) {
                const button = document.createElement('button');
                button.className = 'nav-button'; // Re-use style from main nav for consistency or create new
                button.textContent = \`Jour \${i}\`;
                button.dataset.day = i;
                button.onclick = () => openTab(\`jour\${i}\`);
                dayButtonsContainer.appendChild(button);
            }
        }
        
        document.addEventListener('DOMContentLoaded', () => {
            loadProgress();
            document.querySelectorAll('.sidebar-week-btn').forEach(button => {
                button.addEventListener('click', () => openWeek(button.dataset.week));
            });
            
            const initialDay = userProgress.currentDay;
            const initialWeekNumber = Math.ceil(initialDay / 7);
            const initialWeekId = \`week\${initialWeekNumber}\`;
            openWeek(initialWeekId, initialDay); // This will also call openTab for the specific day.

            const backToTopBtn = document.getElementById('back-to-top');
            window.addEventListener('scroll', () => backToTopBtn.classList.toggle('visible', window.pageYOffset > 300));
            backToTopBtn.addEventListener('click', (e) => { e.preventDefault(); window.scrollTo({top:0, behavior:'smooth'}); });
            
            const themeToggleBtn = document.getElementById('theme-toggle');
            function loadPageTheme() {
                const currentTheme = localStorage.getItem('theme-${slug}');
                if (currentTheme) {
                    document.body.classList.add(currentTheme);
                    if (themeToggleBtn) themeToggleBtn.textContent = currentTheme === 'dark-mode' ? '☀️' : '🌙';
                } else {
                     if (themeToggleBtn) themeToggleBtn.textContent = '🌙'; // Default to light
                }
            }
            if(themeToggleBtn){
                themeToggleBtn.addEventListener('click', () => {
                    document.body.classList.toggle('dark-mode');
                    let theme = document.body.classList.contains('dark-mode') ? 'dark-mode' : 'light-mode';
                    themeToggleBtn.textContent = theme === 'dark-mode' ? '☀️' : '🌙';
                    localStorage.setItem('theme-${slug}', theme);
                });
            }
            loadPageTheme();
        });
    </script>
</body>
</html>`;
    downloadFile(`cours-21-jours_${slug}.html`, html);
  };
  

  // --- Render Form ---
  const renderFormSection = (title, fields) => (
    <div className="mb-8 p-6 bg-white shadow-lg rounded-lg">
      <h2 className="text-2xl font-semibold text-indigo-700 mb-6 border-b pb-2">{title}</h2>
      {fields}
    </div>
  );

  const renderTextInput = (label, group, field, value, placeholder = "") => (
    <div className="mb-4" key={field}>
      <label className="block text-gray-700 text-sm font-bold mb-2" htmlFor={`${group}-${field}`}>
        {label}
      </label>
      <input
        className="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:ring-2 focus:ring-indigo-500"
        id={`${group}-${field}`}
        type="text"
        value={value}
        placeholder={placeholder}
        onChange={(e) => handleInputChange(
            group === 'general' ? setGeneralSettings : 
            group === 'index' ? setIndexSettings : 
            group === 'alphabet' ? setAlphabetSettings : 
            group === 'vocabulary' ? setVocabularySettings : 
            setCourseSettings, 
            group, field, e.target.value
        )}
      />
    </div>
  );
  
 const renderColorInput = (label, group, field, value) => (
    <div className="mb-4" key={field}>
      <label className="block text-gray-700 text-sm font-bold mb-1" htmlFor={`${group}-${field}`}>
        {label}
      </label>
      <div className="flex items-center">
        <input
          className="shadow-sm appearance-none border rounded-l w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:ring-2 focus:ring-indigo-500"
          id={`${group}-${field}`}
          type="text"
          value={value}
          onChange={(e) => handleInputChange(
            group === 'general' ? setGeneralSettings : 
            (setter) => {}, // Should not happen for color
            group, field, e.target.value
          )}
        />
        <input
          type="color"
          value={value}
          className="rounded-r h-10 w-12 cursor-pointer"
          onChange={(e) => handleInputChange(
            group === 'general' ? setGeneralSettings : 
            (setter) => {},
            group, field, e.target.value
          )}
        />
      </div>
    </div>
  );

  const renderTextarea = (label, group, field, value, placeholder = "", rows = 3, helpText = "") => (
    <div className="mb-4" key={field}>
      <label className="block text-gray-700 text-sm font-bold mb-2" htmlFor={`${group}-${field}`}>
        {label}
      </label>
      <textarea
        className="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:ring-2 focus:ring-indigo-500"
        id={`${group}-${field}`}
        rows={rows}
        value={value}
        placeholder={placeholder}
        onChange={(e) => handleTextareaChange(
            group === 'general' ? setGeneralSettings : 
            group === 'index' ? setIndexSettings : 
            group === 'alphabet' ? setAlphabetSettings : 
            group === 'vocabulary' ? setVocabularySettings : 
            setCourseSettings, 
            field, e.target.value
        )}
      />
      {helpText && <p className="text-xs text-gray-500 mt-1 whitespace-pre-line">{helpText}</p>}
    </div>
  );


  return (
    <div className="min-h-screen bg-gradient-to-br from-indigo-100 via-purple-50 to-pink-100 p-4 sm:p-8">
      <div className="max-w-4xl mx-auto bg-white shadow-2xl rounded-xl overflow-hidden">
        <header className="bg-gradient-to-r from-indigo-600 to-purple-600 p-6 sm:p-8 text-white">
          <h1 className="text-3xl sm:text-4xl font-bold text-center">Générateur de Site d'Apprentissage de Langues</h1>
          <p className="text-center text-indigo-200 mt-2">Créez vos propres sites d'apprentissage facilement!</p>
        </header>

        <nav className="flex border-b">
          {['Général', 'Index', 'Alphabet', 'Vocabulaire', 'Cours 21 Jours'].map((tabName, idx) => {
            const tabId = tabName.toLowerCase().replace(/\s+/g, '');
            return (
              <button
                key={tabId}
                onClick={() => setActiveTab(tabId)}
                className={`py-3 px-4 sm:px-6 font-medium text-sm sm:text-base focus:outline-none transition-colors duration-200
                  ${activeTab === tabId ? 'border-b-2 border-indigo-500 text-indigo-600' : 'text-gray-500 hover:text-indigo-500'}`}
              >
                {tabName}
              </button>
            );
          })}
        </nav>

        <main className="p-6 sm:p-8">
          {activeTab === 'general' && renderFormSection('Paramètres Généraux', <>
            {renderTextInput('Nom du Site (e.g., "Apprendre l\'Espagnol")', 'general', 'languageName', generalSettings.languageName)}
            {renderTextInput('Langue Cible (e.g., "Espagnol")', 'general', 'targetLanguage', generalSettings.targetLanguage)}
            {renderTextInput('Langue Native (e.g., "Français")', 'general', 'nativeLanguage', generalSettings.nativeLanguage)}
            <h3 className="text-lg font-semibold text-gray-700 mt-6 mb-2">Couleurs du drapeau (style en-tête)</h3>
            <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
                {renderColorInput('Couleur 1 Drapeau', 'general', 'flagColor1', generalSettings.flagColor1)}
                {renderColorInput('Couleur 2 Drapeau', 'general', 'flagColor2', generalSettings.flagColor2)}
                {renderColorInput('Couleur 3 Drapeau', 'general', 'flagColor3', generalSettings.flagColor3)}
            </div>
             <h3 className="text-lg font-semibold text-gray-700 mt-6 mb-2">Couleurs du Thème (CSS Variables)</h3>
            <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
                {renderColorInput('Primaire (--primary)', 'general', 'themePrimary', generalSettings.themePrimary)}
                {renderColorInput('Secondaire (--secondary)', 'general', 'themeSecondary', generalSettings.themeSecondary)}
                {renderColorInput('Accent (--accent)', 'general', 'themeAccent', generalSettings.themeAccent)}
                {renderColorInput('Clair (--light)', 'general', 'themeLight', generalSettings.themeLight)}
                {renderColorInput('Sombre (--dark)', 'general', 'themeDark', generalSettings.themeDark)}
                {renderColorInput('Fond (--background)', 'general', 'themeBackground', generalSettings.themeBackground)}
                {renderColorInput('Fond Carte (--card-bg)', 'general', 'themeCardBg', generalSettings.themeCardBg)}
                {renderColorInput('Texte Langue Cible (--russe)', 'general', 'themeRusse', generalSettings.themeRusse)}
                {renderColorInput('Texte Langue Native (--francais)', 'general', 'themeFrancais', generalSettings.themeFrancais)}
            </div>
          </>)}

          {activeTab === 'index' && renderFormSection('Page d\'Accueil (index.html)', <>
            {renderTextInput('Titre Introduction', 'index', 'introTitle', indexSettings.introTitle)}
            {renderTextarea('Paragraphe Introduction', 'index', 'introParagraph', indexSettings.introParagraph, "", 4)}
            <h3 className="text-lg font-semibold text-gray-700 mt-6 mb-2">Aperçu Programme 21 Jours</h3>
            {renderTextInput('Titre Semaine 1', 'index', 'week1Title', indexSettings.week1Title)}
            {renderTextarea('Résumé Semaine 1', 'index', 'week1Summary', indexSettings.week1Summary, "", 2)}
            {renderTextInput('Titre Semaine 2', 'index', 'week2Title', indexSettings.week2Title)}
            {renderTextarea('Résumé Semaine 2', 'index', 'week2Summary', indexSettings.week2Summary, "", 2)}
            {renderTextInput('Titre Semaine 3', 'index', 'week3Title', indexSettings.week3Title)}
            {renderTextarea('Résumé Semaine 3', 'index', 'week3Summary', indexSettings.week3Summary, "", 2)}
             <h3 className="text-lg font-semibold text-gray-700 mt-6 mb-2">Ressources Complémentaires</h3>
            {renderTextInput('Applications (séparées par virgule)', 'index', 'resourcesApps', indexSettings.resourcesApps)}
            {renderTextInput('Livres (séparés par virgule)', 'index', 'resourcesBooks', indexSettings.resourcesBooks)}
            {renderTextInput('Sites Web (séparés par virgule)', 'index', 'resourcesWebsites', indexSettings.resourcesWebsites)}
            <button onClick={generateIndexHTML} className="mt-6 w-full bg-green-500 hover:bg-green-600 text-white font-bold py-3 px-4 rounded-lg transition-colors duration-200">
              Générer index.html
            </button>
          </>)}
          
          {activeTab === 'alphabet' && renderFormSection('Page Alphabet', <>
            {renderTextInput('Titre Page Alphabet', 'alphabet', 'pageTitle', alphabetSettings.pageTitle)}
            {renderTextarea('Sous-titre Page Alphabet', 'alphabet', 'pageSubtitle', alphabetSettings.pageSubtitle, "", 2)}
            {renderTextInput('Titre Boîte Info Alphabet', 'alphabet', 'introBoxTitle', alphabetSettings.introBoxTitle)}
            {renderTextarea('Contenu Boîte Info Alphabet', 'alphabet', 'introBoxContent', alphabetSettings.introBoxContent, "Décrivez l'alphabet...", 5)}
            {renderTextarea('Astuces d\'Apprentissage (chaque astuce sur une nouvelle ligne)', 'alphabet', 'learningTips', alphabetSettings.learningTips, "Astuce 1\nAstuce 2...", 5)}
            {renderTextarea('Données des Lettres', 'alphabet', 'lettersData', alphabetSettings.lettersData, "", 15, 
            'Format par ligne : Maj;min;[prononciation];comme "exemple";Type;mot1,[pron1],trad1|mot2,[pron2],trad2\nTypes: Identique, Piège, Unique. Les exemples de mots sont optionnels.\nExemple : A;a;[a];comme "ami";Identique;apple,[apəl],pomme|ant,[ænt],fourmi'
            )}
            <button onClick={generateAlphabetHTML} className="mt-6 w-full bg-green-500 hover:bg-green-600 text-white font-bold py-3 px-4 rounded-lg transition-colors duration-200">
              Générer alphabet.html
            </button>
          </>)}

          {activeTab === 'vocabulaire' && renderFormSection('Page Vocabulaire', <>
            {renderTextInput('Titre Page Vocabulaire', 'vocabulary', 'pageTitle', vocabularySettings.pageTitle)}
            {renderTextarea('Sous-titre Page Vocabulaire', 'vocabulary', 'pageSubtitle', vocabularySettings.pageSubtitle, "", 2)}
            {renderTextInput('Placeholder Recherche', 'vocabulary', 'searchPlaceholder', vocabularySettings.searchPlaceholder)}
            {renderTextarea('Catégories (une par ligne: id,Nom)', 'vocabulary', 'categoriesData', vocabularySettings.categoriesData, "basics,Bases\ngreetings,Salutations", 5)}
            {renderTextarea('Mots de Vocabulaire (un par ligne)', 'vocabulary', 'wordsData', vocabularySettings.wordsData, "", 15, 
            'Format: MotCible;[prononciation];TraductionNative;catégorie1,catégorie2;Nuance (optionnel)\nExemple: Maison;[mɛzɔ̃];House;basics,housing;Peut aussi signifier "foyer".'
            )}
            <button onClick={generateVocabularyHTML} className="mt-6 w-full bg-green-500 hover:bg-green-600 text-white font-bold py-3 px-4 rounded-lg transition-colors duration-200">
              Générer vocabulaire.html
            </button>
          </>)}

          {activeTab === 'cours21jours' && renderFormSection('Page Cours 21 Jours', <>
            {renderTextInput('Titre Page Cours', 'course', 'pageTitle', courseSettings.pageTitle)}
            {renderTextInput('Texte de Progression (ex: "jours complétés")', 'course', 'progressText', courseSettings.progressText)}
            {renderTextarea('Données des Semaines (une par ligne: Titre;Objectif)', 'course', 'weeksData', courseSettings.weeksData, "", 4,
            'Exemple: Semaine 1: Les Fondamentaux;Se familiariser avec l\'alphabet...'
            )}
            {renderTextarea('Données des Jours (séparer chaque jour par "__DAY_SEPARATOR__")', 'course', 'daysData', courseSettings.daysData, "", 20,
            'Format Jour: Numéro;Titre;Objectif\nFormat Section (sur nouvelle ligne): TYPE|Titre(optionnel)|Contenu/Données\nTypes: TEXT_SECTION, LETTER_GRID, VOCAB_LIST, NOTE_BOX, FOCUS_BOX, EXERCISE, DIALOGUE, RECAP_LIST\nExemple Jour 1:\n1;Intro Alphabet;Apprendre A-C\nTEXT_SECTION|Bienvenue|Voici les premières lettres.\nLETTER_GRID|Lettres A à C|A,a,[a],ami|B,b,[b],balle\n__DAY_SEPARATOR__'
            )}
            {renderTextInput('Titre Félicitations', 'course', 'congratsTitle', courseSettings.congratsTitle)}
            {renderTextarea('Message Félicitations', 'course', 'congratsMessage', courseSettings.congratsMessage, "", 3)}
            {renderTextarea('Accomplissements (un par ligne)', 'course', 'congratsAchievements', courseSettings.congratsAchievements, "", 3)}
             <button onClick={generateCourseHTML} className="mt-6 w-full bg-green-500 hover:bg-green-600 text-white font-bold py-3 px-4 rounded-lg transition-colors duration-200">
              Générer cours-21-jours.html
            </button>
          </>)}

        </main>
        <footer className="p-6 bg-gray-50 border-t text-center">
            <p className="text-sm text-gray-500">Language Learning Site Generator - Gemini 2024</p>
        </footer>
      </div>
    </div>
  );
}
