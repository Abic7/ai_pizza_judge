# 🍕 ai_pizza_judge - Professional Pizza Evaluation WebApp

> Because your pizza deserves a fair trial by an AI jury of its peers (trained on the finest Neapolitan standards, naturally).

## What is this madness?

Ever look at a pizza and think, "Is this actually good, or am I just hungry?" Well, wonder no more! pizza_judge is a professional pizza evaluation system that uses AI vision models to judge your pizza with the same ruthless standards employed by the world's most discerning pizza critics.

Upload a photo of your pizza, and our AI—trained in the ancient ways of 50 Top Pizza methodology—will dissect every aspect of your pie: from dough fermentation to leopard spotting, from ingredient quality to that all-important cornicione puff. You'll get a brutally honest 1-10 star rating with detailed technical feedback that'll make you either proud or question your life choices.

**Warning**: This app has opinions. Strong ones. It will not be gentle with your frozen pizza.

## ✨ Features

- 🎯 **Professional Evaluation**: Based on real-world pizza ranking criteria used by 50 Top Pizza
- ⭐ **1-10 Star Rating System**: With breakdown by category (Dough, Cooking, Ingredients, Composition, Presentation)
- 🤖 **AI-Powered**: Runs on your local LM Studio instance with vision-capable models
- 🚫 **Non-Pizza Detection**: Upload a cat? A traffic cone? Get roasted with sarcastic wit
- 📱 **Mobile-Optimized**: Clean, professional interface that works on any device
- 🔧 **Fully Configurable**: Point it at any LM Studio endpoint
- 🎨 **Beautiful UI**: Minimal, elegant design worthy of your artisanal sourdough crust

## 🎭 The "Not Pizza" Experience

Try uploading something that's *not* a pizza. Go ahead. The app will:
1. Immediately detect your shenanigans
2. Serve you a hilariously sarcastic rejection message
3. Judge you silently

Example responses:
- *"Nice try, but orange plastic isn't a topping we recognize. Unless you're going for 'construction site chic'?"*
- *"I'm a pizza evaluator, not a miracle worker. This isn't even close to pizza!"*
- *"That's definitely not a pizza. Did you upload the wrong file, or are you testing my patience?"*

## 🚀 Quick Start

### Prerequisites

1. **LM Studio** - Download from [lmstudio.ai](https://lmstudio.ai)
2. **Vision-capable model** - Tested and working with:
   - `llava-llama-3-8b-v1_1` ✅ (Recommended)
   - `bakllava` models
   - Other LLaVA variants

### Installation

1. Clone this repo:
```bash
git clone https://github.com/Abic7/ai_pizza_judge.git
cd ai_pizza_judge
```

2. That's it. No dependencies. No build process. Just open the HTML file.

### LM Studio Setup

1. **Download and install LM Studio** from [lmstudio.ai](https://lmstudio.ai)

2. **Download a vision model**:
   - Open LM Studio
   - Go to the "Search" tab
   - Search for `llava-llama-3-8b-v1_1`
   - Download the model (recommended: Q4_K_M quantization for best speed/quality balance)

3. **Load the model**:
   - Go to "Chat" tab
   - Select your downloaded LLaVA model from the dropdown
   - Wait for it to load into memory

4. **Start the local server**:
   - Go to "Developer" → "Local Server" tab
   - Click "Start Server"
   - Default endpoint: `http://localhost:1234/v1/chat/completions`
   - **Important**: Enable CORS in the server settings!
     - Click the settings icon in the server tab
     - Check "Enable CORS"
     - This allows the web app to communicate with the API

5. **Adjust settings** (recommended):
   - Temperature: 0.3 (for consistent JSON output)
   - Max tokens: 1500+
   - Keep context size at default

### Running the App

1. Open `pizza-rater.html` in your browser
2. Verify LM Studio is running (check the endpoint field)
3. Upload a pizza photo
4. Get judged

**That's it!** The entire app runs locally in your browser, talking to your local LM Studio instance.

## 📊 Evaluation Criteria

Based on [50 Top Pizza](https://www.50toppizza.it/en/) standards, the world's most authoritative pizza ranking:

### Categories (Total: 10 points)

1. **Dough & Fermentation** (2.5 pts)
   - Evidence of proper long fermentation (12-72 hours)
   - Crust structure: leopard spotting, air pockets, elasticity
   - Texture: proper chewiness balanced with softness
   - Edge (cornicione): puffiness and char

2. **Cooking Technique** (2.5 pts)
   - Leopard spotting from high-heat cooking (900°F+)
   - Even browning across surface
   - Proper cook-through without burning
   - Temperature indicators

3. **Ingredient Quality** (2.5 pts)
   - Cheese quality (fior di latte/buffalo mozzarella standard)
   - San Marzano tomato indicators
   - Topping freshness and authenticity
   - Premium/DOP ingredient evidence

4. **Build & Composition** (1.5 pts)
   - Sauce distribution and quantity
   - Cheese placement (not overloaded)
   - Topping balance and ratio
   - Harmonious assembly

5. **Presentation** (1.0 pt)
   - Overall visual appeal
   - Photo quality
   - Adherence to traditional standards

### Scoring Guide

- **6.5-7.5 ⭐**: Good quality pizza (your local spot is doing alright)
- **7.6-8.5 ⭐**: Excellent pizza (worth driving across town for)
- **8.6-10.0 ⭐**: Exceptional, world-class pizza (book a flight)

**Note**: The AI is calibrated to be realistic. Not every pizza deserves a 9. Most good pizzas score in the 6.0-8.0 range. If you get an 8.5+, you've found something special.

## 🎨 Screenshots

### Upload Interface
![Upload Interface](https://github.com/Abic7/ai_pizza_judge/blob/main/ai_pizza_Judge_ui.png?raw=true)

**What you'll see:**
- Clean, professional upload interface
- Real-time evaluation with loading state
- Star rating with detailed category breakdown
- Expandable "More Details" section
- Professional assessment summary

## 🛠️ How It Works

### The Tech Stack (or lack thereof)

- **Frontend**: Pure HTML/CSS/JavaScript (no frameworks, no build tools)
- **Fonts**: Google Fonts (Cormorant Garamond + Inter)
- **AI**: Your local LM Studio instance with vision models
- **API**: OpenAI-compatible endpoint (LM Studio's built-in server)

### The Flow

1. **Upload**: User selects/drops pizza image
2. **Validation**: AI checks if it's actually pizza
   - If NO → Funny sarcastic message
   - If YES → Continue to evaluation
3. **Analysis**: AI evaluates across 5 categories using professional criteria
4. **Display**: Results shown with animated star rating and detailed breakdown
5. **Reset**: User can evaluate another pizza

### Why Local AI?

- **Privacy**: Your pizza photos never leave your machine
- **Speed**: No API rate limits or costs
- **Control**: Use any model you want
- **Offline**: Works without internet (after initial model download)

## 🔧 Configuration

### Changing the API Endpoint

The app defaults to `http://localhost:1234/v1/chat/completions`, but you can change this:

1. Open the app
2. Modify the "LM Studio API Endpoint" field
3. Start evaluating

### Using Different Models

The app works with any OpenAI-compatible vision model. Tested models:
- ✅ `llava-llama-3-8b-v1_1` (recommended)
- ✅ `bakllava-1` 
- ✅ Other LLaVA variants

**Note**: Smaller/older models may struggle with JSON formatting. Use at least an 8B parameter model for best results.

### Adjusting Evaluation Strictness

The AI prompt is embedded in the HTML. To adjust how harsh/lenient it is:

1. Open `pizza-rater.html` in a text editor
2. Find the prompt section (search for "professional pizza evaluator")
3. Modify the scoring guidance
4. Save and reload

## ⚠️ Known Issues & Limitations

### Common Problems

**"JSON.parse: bad escaped character" Error**
- **Cause**: Model generating malformed JSON
- **Solution**: Lower temperature in LM Studio to 0.3 or use a larger/better model

**"CORS Error" or "Failed to fetch"**
- **Cause**: CORS not enabled in LM Studio
- **Solution**: Go to LM Studio server settings → Enable CORS

**AI evaluates non-pizza as pizza**
- **Cause**: Model not sophisticated enough to validate
- **Solution**: Use a better vision model (llava-llama-3-8b works well)
- **Fallback**: App has confidence threshold - low confidence triggers error

**Slow evaluation (30+ seconds)**
- **Cause**: Model too large for your hardware or not GPU-accelerated
- **Solution**: Use a smaller quantization (Q4 instead of Q8) or enable GPU in LM Studio

### Limitations

- **Image Quality Matters**: Blurry photos = unreliable evaluations
- **Pizza Types**: Optimized for Neapolitan/traditional pizzas. Deep dish might confuse it.
- **Subjective Taste**: AI can't taste your pizza (yet). Visual analysis only.
- **Model Dependency**: Results vary by model quality. Better models = better evaluations.

## 🤝 Contributing

Found a bug? Want to add features? PRs welcome!

### Ways to Contribute

1. **Test with different models** - Share your results
2. **Improve the AI prompt** - Make evaluations more accurate
3. **Add features** - Save evaluations, compare pizzas, export reports
4. **UI improvements** - Better animations, dark mode, themes
5. **Documentation** - Better setup guides, troubleshooting tips

### Contribution Guidelines

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Test your changes with actual pizza photos
4. Commit with clear messages (`git commit -m 'Add ability to save evaluations'`)
5. Push to your branch (`git push origin feature/amazing-feature`)
6. Open a Pull Request

**Please ensure**:
- Code is clean and commented
- Works with `llava-llama-3-8b-v1_1` model minimum
- Mobile-friendly (if UI changes)
- No external dependencies added (keep it simple!)

## 📝 License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details.

**TL;DR**: You can use, modify, and distribute this freely, but any modifications must also be open source under GPL.

## 👨‍💻 Author

**Abic7**

Built with frustration over mediocre pizzas and fascination with AI vision models.

##  Acknowledgments

- **50 Top Pizza** - For establishing world-class pizza evaluation standards
- **LM Studio Team** - For making local AI accessible
- **LLaVA Project** - For excellent open-source vision models
- **Every pizzaiolo** - Who inspired this through their craft

## 🍕 Philosophy

Good pizza is an art form. It deserves to be evaluated with the same rigor we apply to fine dining, wine, or coffee. This app brings professional pizza criticism to everyone with a camera phone and a local AI model.

Whether you're a home pizza maker perfecting your sourdough starter, a pizzeria owner quality-checking consistency, or just someone who wants to settle the "is this pizza actually good" debate—pizza_judge is your unbiased AI judge.

**Remember**: The app is harsh because excellence is rare. A 7.5 is genuinely good. An 8.5+ is exceptional. Don't get discouraged—use the feedback to improve!

---

*Now go forth and photograph pizzas. May your leopard spotting be plentiful and your cornicione be puffy.* 🍕✨
