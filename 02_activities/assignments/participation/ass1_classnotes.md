Why Data Visualization Matters 

Data science insights lose impact if not communicated clearly. 

Visuals often convey complex information better than text/numbers. 

Historical case studies:  

John Snow (1854): Cholera map traced outbreak to a water pump → origin of epidemiology. 

Florence Nightingale (1858): Rose diagram showing soldier deaths → advocated for better army medicine. 

Charles Minard (1869): Napoleon’s Russian campaign losses → storytelling through visualization. 

 

 

Case Study: Challenger Disaster (1986) 

Shuttle exploded due to O-ring failure. 

Edward Tufte (1997) argued poor visualization hid risks; his graph showed O-ring damage increased at lower temperatures. 

Debate: Robison later claimed Tufte misrepresented data. 

Lesson: Visualization choices can save lives—or mislead. 

 

 

What Makes a “Good” Visualization 

Aesthetic: Pleasing to look at. 

Substantive: Accurate and honest representation of data. 

Perceptual: Clear message, easy to understand. 

Must consider context, audience, and data structure. 

No universal rules—requires judgment. 

 

 

Tools for Data Visualization 

Excel / Google Sheets / LibreOffice Calc  

Easy, point-and-click, static visuals. 

Common “first-line” tool. 

Tableau / Tableau Public  

Interactive, dynamic dashboards. 

Paid (except Tableau Public). 

Power BI  

Business intelligence, drag-and-drop visuals. 

Paid, industry/government use. 

R  

Free, reproducible, coding required. 

Libraries: ggplot2, Plotly, RColorBrewer. 

Python  

Free, reproducible, coding required. 

Libraries: Matplotlib, Plotly, Seaborn. 

 

 

Course Focus 

Step-by-step walkthroughs in Python (Matplotlib). 

General design principles apply across tools. 



Introduction to Matplotlib 

Basics 

Matplotlib: Open-source Python package for data visualization (created 2003, inspired by Matlab). 

Figure: Container for plots. 

Axes: The actual plot/graph inside a figure. 

Artists: Visual elements (lines, labels, legends, ticks, etc.) belong to axes. 

 

 

Anatomy of a Figure 

Figure → plt.figure() 

Axes → fig.subplots() 

Title → ax.set_title() 

Labels → ax.set_xlabel(), ax.set_ylabel() 

Ticks → ax.xaxis, ax.yaxis (major/minor locators & formatters) 

Grid → ax.grid() 

Legend → ax.legend() 

Lines/Markers → ax.plot(), ax.scatter() 

 

 

Creating Plots 

Import libraries: numpy, matplotlib.pyplot, pandas, scipy, PIL, requests 

Sample data: np.random.seed(613) x = np.arange(50) y = np.random.randint(0, 100, 50)  

Basic plots:  

Scatter → ax.scatter(x, y) 

Bar → ax.bar(x, y) 

Line → ax.plot(x, y) 

Histogram → ax.hist(y) 

 

 

Labels & Titles 

Add labels: ax.set_title("Title") ax.set_xlabel("X-axis") ax.set_ylabel("Y-axis")  

Customize with fontdict (family, color, size). 

Position labels with loc. 

 

 

Customizing Appearance 

Markers: marker='*', markersize=12 

Colors: Named colors or hex codes (color="#7425b9") 

Lines: linestyle='--', linewidth=2 

Marker edges/faces: markeredgecolor, markerfacecolor 

Gridlines: ax.grid(axis='y', color="blue", linewidth=2, linestyle='-.') 

 

 
Reproducible Data Visualization 

Why Reproducibility Matters 

Case Study (2016 cancer research images):  

Images were manipulated → paper retracted. 

Dr. Elisabeth Bik uncovered duplications → led to 172 retractions, 300+ corrections. 

Shows how untrustworthy visuals undermine science. 

Key Point: If visualizations don’t represent real data, we can’t trust conclusions. 

 

 

What is Reproducibility? 

Work is reproducible if data, code, and methods are available for others to check. 

Someone should be able to repeat steps and get the same result. 

Increasingly required in academic and professional contexts. 

Ethical: Transparency and accountability in decisions. 

Practical: Easier editing, version control, reuse of past work. 

 

 

Best Practices for Reproducible Visualization 

Work programmatically  

Use code (R, Python) instead of manual tools (Illustrator). 

Use plain text  

Scripts (.py, .R, .txt), not Word docs. 

Final plots should be generated directly from code. 

Comment your code  

Explain choices, make it understandable for future use. 

Follow FAIR principles  

Findability, Accessibility, Interoperability, Reusability. 

Ensures datasets can be located, accessed, and reused. 

 

 

Key Terms 

Reproducibility: Same results using same data, code, and methods. 

Replicability: Consistent results across independent studies with new data. 

Reusability: Others can reuse your dataset and methods. 

 


Choosing the Right Visualization 

Core Idea 

Choosing the right visualization depends on purpose, audience, medium, and data type. 

Visualizations are never fully neutral—design choices shape perception. 

Goal: balance aesthetic, substantive, and perceptual qualities. 

 

 

Case Studies 

Gun Violence (Periscopic, 2018): Emotional visualization showing “years stolen” → persuasive, supports a cause. 

Washington Post Active Shooter Chart: Neutral bar chart → “blank page” style, lets audience interpret. 

NYT Jobs Report (2012): Same data shown differently for Republican vs. Democrat perspectives → both factual, but framed differently. 

Lesson: Visualizations can be factual but not neutral; they are rhetorical objects. 

 

 

Key Principles 

Visualization Qualities:  

Aesthetic → pleasing to look at. 

Substantive → accurate and honest. 

Perceptual → clear message. 

Purpose: Persuading, comparing, evaluating, exploring. 

Audience: Age, education, expertise, accessibility. 

Medium: Print, web, poster, presentation. 

Dataset Types: Tables, networks, fields, geometries, trees. 

Attribute Types: Categorical, ordinal, quantitative; ordering can be sequential, diverging, cyclic. 

 

 

Cognitive Psychology in Visualization 

Gestalt Principles:  

Proximity, similarity, continuity, closure, enclosure, connection → guide how people group and interpret visuals. 

Cognitive Load:  

Intrinsic (complexity of info), germane (audience familiarity), extraneous (presentation style). 

Reduce extraneous load by using familiar chart types, clear layouts, side-by-side comparisons. 

Avoid 3D charts unless necessary → increases cognitive load and misleads. 

 

 

Perceived Objectivity 

Conventions that reinforce trust:  

2D images, clean layouts, geometric shapes, cited data sources. 

Provenance rhetoric: Including sources signals transparency and increases persuasiveness. 

 

 

Resources for Choosing Visualization Types 

Data Visualization Catalogue: Charts categorized by function (comparison, proportion, relationship, hierarchy). 

Financial Times Visual Vocabulary: Interactive guide linking chart types to functions (deviation, correlation, ranking, distribution, change over time, part-to-whole, magnitude, spatial, flow). 

 

Customizing Plots in Matplotlib 

Key Customization Features 

Legends 

Add labels with label argument in ax.plot() or ax.scatter(). 

Display with ax.legend(loc='lower right'). 

Modify with arguments: frameon, fontsize, ncol, shadow. 

Move outside plot using bbox_to_anchor. 

Text & Annotations 

Add text with ax.text(x, y, "message"). 

Customize with alignment (ha), color, size. 

Position relative to data, axes, or figure using transforms (transData, transAxes, transFigure). 

Use ax.annotate() for arrows + text → highlight important points. 

Arrow styles customizable with arrowprops. 

Axis Labels & Ticks 

Remove ticks/labels: NullLocator() or NullFormatter(). 

Limit ticks: MaxNLocator(n). 

Set intervals: MultipleLocator(interval). 

Rotate labels: plt.xticks(rotation=45, ha='right'). 

Customize axis titles with plt.xlabel() and fontdict. 

Styles 

Pre-made styles change multiple aesthetics at once. 

View available styles: plt.style.available. 

Apply style: plt.style.use('fivethirtyeight'). 

Styles affect colors, gridlines, fonts, etc. 

 

Subplots & Combining Visualizations (Matplotlib) 

Key Concepts 

Figures & Axes  

Figure = container; Axes = actual plot. 

Multiple axes (subplots) can be arranged in grids or mosaics. 

All visual elements (labels, legends, text, etc.) belong to axes. 

 

 

Subplots 

Basic grid subplots: fig, (ax1, ax2) = plt.subplots(ncols=2, nrows=1, figsize=(7,3))  

Example: scatter plot on ax1, bar chart on ax2. 

Mosaic layout:  

Use plt.subplot_mosaic() for flexible arrangements. 

Reference axes by labels (someaxes["ax1"]). 

 

 

Layout Adjustments 

Problem: Large labels/titles can overlap or get cut off. 

Solutions:  

tight_layout() → adjusts spacing for labels/ticks. 

constrained_layout=True → also fits legends/colorbars neatly. 

 

 

Combining Visualizations 

Multiple plots on one axes:  

Call multiple plot methods on the same ax. 

Example: ax.bar() + ax.plot() together. 

Add annotations, shapes, etc. as usual. 

 

 

Error Information 

Add error bars: ax.errorbar(x, y, yerr=y_sd, fmt="none")  

Customize with ecolor, elinewidth, capsize, capthick. 

Use errorevery to show error bars at intervals. 

 

 

Adding Images 

Load images with PIL + requests. 

Overlay image axes on figure: ax_image = fig.add_axes([x, y, width, height]) ax_image.imshow(image) ax_image.axis('off')  

Useful for combining graphics with plots (e.g., character images + data). 

 

 

Saving Visualizations 

Save with: plt.savefig(path+filename, dpi=300)  


Accessible Data Visualization 

Why Accessibility Matters 

Inaccessible visualizations exclude audiences and can even harm them. 

Case studies:  

Daily Routines of Famous Creative People → looks good but fails for colourblind users (no labels, colours indistinguishable). 

Flattening the Curve (COVID-19) → effective for many, but inaccessible to people with visual impairments (no alt-text, no tactile versions). 

Accessibility is both an ethical responsibility and a practical necessity. 

 

 

Government of Canada Principles 

Make information clear, concise, easy to use. 

Present in predictable, barrier-free ways. 

Provide barrier-free interaction. 

Ensure compatibility with assistive technologies. 

 

 

Practical Guidelines 

Colour 

Use luminance (brightness) and saturation for ordered data. 

Use hue for categorical data. 

Larger areas = easier colour distinction. 

Test with colour blindness simulators. 

Maintain contrast (check with WebAIM Contrast Checker). 

Use Viridis colormap (works in R and Python) → colourblind-friendly, readable in grayscale. 

Don’t rely only on colour → add patterns, textures, or labels. 

Text 

Labels & legends: every element should be described. 

Fonts: sans-serif (Arial, Helvetica, Verdana) more accessible; avoid too many typefaces. 

Font size: ≥12pt; spacing matters. 

Monospaced text often easier to read. 

Image Descriptions 

Alt-text: plain language, include essential info. 

For graphs: describe chart type, axes, trends, clusters, context. 

Four levels of description:  

Chart elements (title, labels, colours). 

Stats (mean, outliers, comparisons). 

Trends/patterns (clusters, exceptions). 

Context/interpretation (social/political). 

Blind participants prefer factual (levels 2 & 3) over editorialized (level 4). 

 

 

Technical & Distribution Considerations 

Cross-browser functionality: test in Chrome, Firefox, Edge, Safari. 

Cost barriers: subscription-only publications limit access → use Open Access, Creative Commons. 

User testing: best way to check accessibility. 

 

 
Data Visualization as Advocacy 

Why Advocacy Matters 

Data visualization can be used not just to inform, but to persuade and advocate for causes. 

Examples from history and modern times show how visuals shape public opinion and policy. 

 

 

Historical & Modern Case Studies 

Florence Nightingale (1858): Rose diagram → advocated for better army medicine. 

Gun Killings in the US (Periscopic, 2018): Emotional visualization showing “years stolen” → highlights gun violence. 

Brooks Slave Ship Diagram (1788): Showed inhumane conditions → provoked horror, supported abolition. 

Abolitionist Slogans & Art: Emotional/moral appeals on everyday objects. 

 

 

Modes of Persuasion (Aristotle) 

Rational appeal: Facts and evidence. 

Moral appeal: Ethical values and justice. 

Emotional appeal: Empathy, outrage, compassion. 

Effective advocacy often combines all three. 

 

 

Functions of Advocacy Visuals 

Presentation: Objective depiction of facts. 

Representation: Subjective framing using metaphor, analogy, or emotional cues. 

Most advocacy visuals blend both. 

 

 

Form 

Beyond static charts → new mediums (art, installations, interactive visuals). 

Examples:  

Pulse (2012) → video visualization. 

Watermarks (2009) → public art marking future flood levels. 

Untitled (Ross) (1991) → installation representing loss from AIDS. 

 

 

Representation 

Visualizations are rhetorical objects → choices about what data to show/exclude. 

Example: binary gender data excludes nonbinary identities. 

“What gets counted counts” → but exclusions reinforce power structures. 

Data can include stories, art, lived experiences—not just numbers. 

 

 

Credit 

Visualizations rely on unseen labour (data collectors, designers, IT staff, caregivers, etc.). 

The “Diverse Economies Iceberg” metaphor → much work is invisible. 

Giving credit makes hidden contributions visible and valued. 



 

 

 