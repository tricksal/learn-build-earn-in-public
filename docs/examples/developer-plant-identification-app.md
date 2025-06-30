# Case Study: Building a Plant Identification App

*A Developer's 10-Week Open Source Quest*

---

## Background

**Role:** Frontend developer at a mid-size tech company  
**Challenge:** Wanted to learn mobile development and machine learning while building something meaningful  
**Timing:** Fall 2024, using evenings and weekends  

### The Technical Problem
- Experienced in React web development but new to React Native
- Curious about integrating ML models into mobile apps
- Wanted to contribute to environmental awareness and education
- Needed a portfolio project that demonstrated full-stack capabilities

---

## The Quest

**Quest Title:** "Build a working prototype of a mobile app that helps people identify plants using their camera"

**Duration:** 10 weeks  
**Primary Platform:** GitHub with cross-posting to LinkedIn and Twitter  
**Success Criteria:** 
- Working React Native app with camera integration
- ML model that can identify 50+ common plants
- Open source with comprehensive documentation
- 100+ GitHub stars and meaningful community feedback

---

## Process: LBEiP in Action

### Week 1: Declaration & Architecture Planning

**Sanctuary Session (Monday, Week 1):**
- 90 minutes sketching app architecture and user flow
- Researched existing plant identification APIs and datasets
- Identified key technical challenges: camera integration, ML model deployment, offline functionality

**First Public Post (GitHub README + LinkedIn, Thursday Week 1):**

**GitHub:**
```markdown
# 🌱 PlantID - Open Source Plant Identification App

Starting a 10-week Quest to build a mobile app that helps people identify plants using their camera.

## Why this project?
- Learn React Native and mobile ML integration
- Contribute to environmental education and awareness
- Create something useful for gardeners, hikers, and nature lovers
- Practice building in public and open source development

## What I'll be building:
- React Native app with camera integration
- Plant identification using TensorFlow Lite
- Offline-first design with local plant database
- Clean, accessible UI for all skill levels

## Tech Stack:
- React Native + Expo
- TensorFlow Lite for mobile ML
- SQLite for local plant database
- Node.js backend for model training pipeline

Follow along, contribute, or just watch the journey unfold!

## Current Status: 🚧 Planning Phase
- [x] Initial research and architecture planning
- [ ] Set up development environment
- [ ] Create basic app structure
- [ ] Implement camera functionality

Star ⭐ if you're interested in following this project!
```

**LinkedIn:**
```
Starting a new coding Quest: Building an open source plant identification app! 🌱📱

Why plants? As someone who kills every houseplant I touch, I figured building 
an app to identify them might help me (and others) become better plant parents.

The technical challenge: Integrating machine learning into a mobile app that 
works offline. I'll be learning React Native, TensorFlow Lite, and mobile ML 
deployment along the way.

I'll be building completely in the open on GitHub, sharing code, challenges, 
and learnings as I go. This isn't about having all the answers—it's about 
learning and building something useful.

GitHub repo: [link]

If you're into mobile dev, ML, or just love plants, I'd love your thoughts 
and suggestions!

#ReactNative #MachineLearning #OpenSource #BuildInPublic #LBEiP
```

**Initial Engagement:** 45 GitHub stars, 23 LinkedIn likes, 8 comments with suggestions

### Week 2-3: Environment Setup & Basic App Structure

**Technical Progress:**
- Set up React Native development environment with Expo
- Created basic app navigation structure
- Implemented camera functionality with expo-camera
- Set up CI/CD pipeline with GitHub Actions

**Exploration Post (Week 2, GitHub Discussions + Twitter):**
```
## Week 2 Progress: PlantID App Structure

### What I've built:
- Basic React Native app with Expo
- Camera screen with photo capture
- Navigation between screens
- CI/CD pipeline for automated testing

### What I've learned:
- Expo makes React Native setup much smoother than expected
- Camera permissions on mobile require careful UX consideration
- TypeScript + React Native = much better developer experience

### Current challenges:
- Deciding between Expo managed vs. bare workflow for ML integration
- Finding the right balance between app size and model accuracy
- Designing for both iOS and Android camera differences

### Next steps:
- [ ] Research plant identification datasets
- [ ] Experiment with TensorFlow Lite model conversion
- [ ] Design plant detail screens

Code so far: 847 lines across 12 files
Tests: 15 passing ✅

Feedback and suggestions welcome! What features would you want in a plant ID app?
```

### Week 4-5: Machine Learning Integration

**Technical Deep Dive:**
- Researched PlantNet and iNaturalist datasets
- Experimented with pre-trained MobileNet models
- Built Python pipeline for model training and conversion
- Integrated TensorFlow Lite into React Native app

**Construction Post (Week 4, GitHub + LinkedIn):**

**GitHub:**
```markdown
## Week 4: ML Model Integration Deep Dive

### The Challenge:
Getting a machine learning model to run efficiently on mobile devices while maintaining reasonable accuracy.

### What I tried:
1. **Pre-trained models:** Started with MobileNetV2 trained on ImageNet
2. **Transfer learning:** Fine-tuned on PlantNet dataset (10K plant images)
3. **Model optimization:** Quantized to reduce size from 14MB to 3.5MB

### Results:
- **Accuracy:** 73% on test set (50 common plant species)
- **Inference time:** 280ms on iPhone 12, 450ms on Android mid-range
- **App size impact:** +3.5MB (acceptable for MVP)

### Code snippet - Model integration:
```javascript
import * as tf from '@tensorflow/tfjs';
import '@tensorflow/tfjs-react-native';

const classifyPlant = async (imageUri) => {
  const response = await fetch(imageUri, {}, { isBinary: true });
  const imageData = await response.arrayBuffer();
  const imageTensor = decodeJpeg(new Uint8Array(imageData));
  
  const predictions = await model.predict(imageTensor).data();
  return predictions;
};
```

### What's working:
- Model loads successfully on both platforms
- Predictions are reasonably accurate for common plants
- Offline functionality works as intended

### What's not working yet:
- Accuracy drops significantly for less common species
- Model struggles with partial plant views (just leaves vs. full plant)
- Need better error handling for edge cases

### Next experiments:
- [ ] Try ensemble of specialized models (flowers, leaves, bark)
- [ ] Implement confidence thresholds
- [ ] Add user feedback loop for improving accuracy

Thoughts on the approach? Any ML mobile experts have suggestions?
```

### Week 6-7: UI/UX Development & User Testing

**Design & Development:**
- Created plant identification results screen with confidence scores
- Built plant detail pages with care instructions
- Implemented favorites and history features
- Conducted user testing with 8 friends and family members

**Construction Post (Week 6, Instagram + LinkedIn):**

**Instagram:**
```
The messy middle of app development 📱🌱

Swipe to see:
→ Early wireframes vs. current design
→ User testing session (my mom trying to ID her succulent)
→ The "plant graveyard" - my failed houseplants that inspired this app
→ Code at 2 AM (don't judge the variable names)

Current dilemma: Should the app show multiple possible plant matches or just 
the top prediction? Users want options, but too many choices create decision paralysis.

Testing revealed: People want to know WHY the app thinks it's a certain plant. 
Adding visual indicators for key identifying features.

What would you want to see in a plant ID app? Drop your thoughts below! 👇

#AppDevelopment #PlantID #UserTesting #BuildInPublic #ReactNative
```

### Week 8-9: Polish & Documentation

**Final Development Push:**
- Added plant care reminders and watering schedules
- Implemented offline plant database with 200+ species
- Created comprehensive documentation and contribution guidelines
- Fixed 23 bugs found during beta testing

**Near-Revelation Post (Week 8, GitHub + LinkedIn):**
```
Week 8: PlantID App Beta is Ready! 🎉

After 8 weeks of coding, learning, and iterating, the beta version is live:

📱 **What it does:**
- Identify plants from photos with 73% accuracy
- Works completely offline (no internet required)
- Provides care instructions and watering reminders
- Tracks your plant collection and identification history

🛠️ **Tech highlights:**
- React Native + Expo for cross-platform development
- TensorFlow Lite for on-device ML inference
- SQLite for local plant database (200+ species)
- 2,847 lines of TypeScript across 34 files

📊 **Beta testing results:**
- 12 beta testers across iOS and Android
- Average identification accuracy: 73% (target was 70%)
- App size: 8.2MB (within 10MB target)
- Average rating: 4.2/5 stars

🔧 **What I learned:**
- Mobile ML is more accessible than I expected
- User feedback is crucial - features I thought were important weren't
- Documentation takes longer than coding (but it's worth it)

Try the beta: [TestFlight/Play Store Beta links]
Full source code: [GitHub repo]

What plant should I test it on next? 🌿

#ReactNative #MachineLearning #OpenSource #BetaLaunch #PlantID
```

### Week 10: Launch & Reflection

**Public Launch:**
- Released v1.0 on GitHub with full documentation
- Published to Expo store for easy installation
- Created demo video and comprehensive README
- Submitted to Product Hunt and Hacker News

**Revelation Post (Week 10):**
```
🎉 Quest Complete: PlantID v1.0 is Live!

After 10 weeks of building in public, I'm excited to share:

## PlantID - Open Source Plant Identification App

### What it became:
📱 Cross-platform mobile app (iOS + Android)
🧠 On-device ML model (73% accuracy, 200+ species)
📚 Comprehensive plant care database
🔄 Completely offline functionality
📖 Full documentation + contribution guidelines

### By the numbers:
- **Code:** 3,247 lines of TypeScript
- **Tests:** 89 passing (87% coverage)
- **GitHub:** 247 stars, 31 forks, 12 contributors
- **Users:** 156 beta testers, 4.3/5 average rating

### What I learned:
- **Technical:** Mobile ML deployment, React Native performance optimization
- **Process:** Building in public accelerates learning and attracts contributors
- **Community:** Open source projects succeed through documentation and welcoming contributors

### Unexpected outcomes:
- 3 job interview requests from companies impressed by the public building process
- Collaboration offer from botanical garden for educational version
- Featured in React Native newsletter (15K+ subscribers)

### Try it out:
- 🔗 **Live app:** [Expo store link]
- 📦 **Source code:** [GitHub repo]
- 📚 **Documentation:** [Docs site]

### What's next:
Planning v2.0 with community-requested features:
- [ ] Plant disease identification
- [ ] Social features (share discoveries)
- [ ] Integration with gardening apps

Huge thanks to everyone who starred, contributed, tested, and provided feedback. 
This wouldn't exist without the community! 🙏

**Star ⭐ the repo if you find it useful!**

#OpenSource #ReactNative #MachineLearning #QuestComplete #BuildInPublic
```

**Reflection Post (Week 11):**
```
Reflecting on my PlantID Quest: What 10 weeks of building in public taught me 🌱

Beyond the app I built, here's what this Quest taught me about development and community:

🎯 **About mobile development:**
React Native + ML is more accessible than I expected, but performance optimization 
requires deep platform knowledge. The real challenge isn't the code—it's the UX.

🧠 **About building in public:**
Sharing struggles and failures generated more engagement than sharing successes. 
People connect with the learning process, not just the final product.

🔄 **About open source:**
Good documentation matters more than perfect code. 12 contributors joined because 
the README was clear, not because the architecture was flawless.

📊 **About technical decisions:**
My initial plan (complex ensemble model) was overengineering. The simple approach 
(single MobileNet model) delivered 90% of the value with 50% of the complexity.

The most valuable part wasn't the 247 GitHub stars—it was the 3 job opportunities 
that came from companies seeing my problem-solving process in public.

For anyone considering a similar technical Quest:
👉 Start with the simplest version that solves the core problem
👉 Document your decisions and trade-offs, not just your code
👉 Engage with users early and often—they'll guide your priorities

What's my next Quest? Considering either:
- Building a web version of PlantID with advanced features
- Exploring computer vision for wildlife identification

Thanks to everyone who followed along, contributed, and helped make this better! 🙏

#BuildInPublic #OpenSource #TechnicalReflection #LBEiP #ReactNative
```

---

## Outcomes

### Primary Artifacts Created:
- **PlantID Mobile App** - Cross-platform React Native app with ML integration
- **Open Source Repository** - 3,247 lines of well-documented TypeScript code
- **ML Training Pipeline** - Python scripts for model training and optimization
- **Comprehensive Documentation** - API docs, contribution guidelines, deployment guides

### Quantifiable Results:
- **GitHub Stats:** 247 stars, 31 forks, 12 contributors, 89 closed issues
- **App Usage:** 156 beta testers, 4.3/5 rating, 1,200+ plant identifications
- **Social Media:** 89 LinkedIn likes, 34 Twitter retweets, 156 total engagements
- **Technical Achievement:** 73% ML accuracy, 8.2MB app size, 87% test coverage

### Unexpected Opportunities:
- **Job Interviews:** 3 companies reached out based on public building process
- **Collaboration:** Partnership offer from botanical garden for educational version
- **Media Coverage:** Featured in React Native Weekly newsletter (15K+ subscribers)
- **Speaking:** Invited to present at local React Native meetup

### Technical Learning:
- **Mobile Development:** React Native, Expo, cross-platform considerations
- **Machine Learning:** TensorFlow Lite, model optimization, on-device inference
- **DevOps:** CI/CD for mobile apps, automated testing, beta distribution
- **Open Source:** Community management, documentation, contributor onboarding

---

## Lessons for Other Developer Quest Leaders

### What Worked Well:
1. **Clear technical scope:** Focused on one core feature (plant ID) rather than building a full gardening app
2. **Regular code sharing:** Weekly commits and progress updates kept momentum and attracted contributors
3. **User testing early:** Getting feedback from real users prevented over-engineering
4. **Comprehensive documentation:** Good docs attracted contributors and job opportunities

### What I'd Do Differently:
1. **Start with web version:** Mobile development added complexity that slowed initial progress
2. **More video content:** Code walkthroughs and demo videos would have increased engagement
3. **Better project management:** Should have used GitHub Projects to track progress publicly
4. **Community building:** Could have engaged with React Native and ML communities earlier

### Advice for Similar Technical Quests:
1. **Pick a problem you personally face** - you'll understand the user needs better
2. **Start simple, add complexity gradually** - MVP first, advanced features later
3. **Document your decision-making process** - employers value this more than perfect code
4. **Engage with relevant communities** - don't just build in isolation

---

## Long-term Impact

### Career Development:
- Demonstrated full-stack mobile development capabilities
- Established expertise in mobile ML integration
- Built reputation for clear technical communication and documentation
- Created portfolio piece that directly led to job opportunities

### Open Source Contribution:
- Active repository with ongoing community contributions
- Educational resource for developers learning mobile ML
- Foundation for potential commercial applications or partnerships

### Technical Growth:
- Mastered React Native and mobile development patterns
- Gained practical experience with ML model deployment and optimization
- Learned open source project management and community building
- Developed systematic approach to building in public

---

*This case study demonstrates how technical creators can use the LBEiP framework to learn new technologies, build community, and create career opportunities. The key is balancing technical depth with clear communication and genuine problem-solving.*
