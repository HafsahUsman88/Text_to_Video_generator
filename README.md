# Text_to_Video_generator

## Video Demo
Check out the demonstration of this project in action!

**Link entered:** https://pib.gov.in/PressReleasePage.aspx?PRID=1983683

## Text-to-Video Generation
This project presents a novel pipeline for transforming textual content from notes into engaging videos. It leverages the power of Colab notebooks and pre-trained deep learning models, specifically focusing on the Stable Diffusion XL-Base 1.0 model from Stability AI, to achieve this transformation in a distributed computing environment.

**Workflow:**

1. **Colab Notebook 1: Grad&Master.ipynb**
   - Upon execution, this notebook initiates a web scraping process, dynamically extracting the textual content from a user-provided link using a designated web scraping library (e.g., BeautifulSoup, Scrapy).
   - The extracted content is then fed into a pre-trained tokenizer (`BartTokenizer.from_pretrained("facebook/bart-large-cnn")`) and model (`BartForConditionalGeneration.from_pretrained("facebook/bart-large-cnn")`) from the Hugging Face library. These models perform text processing and generate smaller, focused prompts based on the overall content.
   - The interface at `gradio` facilitates this interaction, seamlessly guiding the user through the process.

2. **Prompt-Driven Image Generation with Stable Diffusion XL-Base 1.0:**
   - The derived prompts, acting as concise instructions, are transmitted to a pre-trained Stable Diffusion XL-Base 1.0 model from Stability AI. This model employs a complex deep learning architecture known as a **diffusion model**. 
3. **Automated Video Assembly (Colab Notebook 2 - Automatically triggered):**
   - A separate Colab notebook, potentially named `Meghana-Adding_audio_n_combine.ipynb`, is automatically triggered once image generation is complete. This notebook is assumed to handle video assembly and audio integration.
   - Specific implementation details may involve the use of video editing libraries like OpenCV or MoviePy. The exact nature of this stage requires further investigation depending on the availability of the second notebook.

4. **Output Video Presentation:**
   - After successful video creation, the final video is displayed on the `gradio` user interface, allowing the user to preview the results of the text-to-video transformation.

**Technical Considerations:**
- Cloud-based execution is facilitated through Colab notebooks, enabling efficient resource utilization and scalability.
- Hugging Face transformers provide a robust framework for text processing, while Stability AI's Stable Diffusion XL-Base 1.0 model leverages a powerful diffusion model architecture for image generation.
- Web scraping techniques require careful consideration of website terms of service and ethical implications.

