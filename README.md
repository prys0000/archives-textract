<p>&nbsp;<br /> <img src="https://github.com/prys0000/archives-textract/raw/main/SIG.png" alt="" width="117" height="107" /></p>
<h1><strong>archives-textract</strong></h1>
<p>The objective of this project is to develop a text extraction and cleaning tool that utilizes the capabilities of Amazon Textract and RapidMiner. The code extracts text from documents stored in an AWS S3 bucket, performs text cleaning operations using RapidMiner, and saves the extracted and cleaned text to Excel files. By automating the text extraction and cleaning processes, this project enables efficient handling of large-scale collections of documents. The use of Amazon Textract and RapidMiner allows for reliable and accurate extraction and cleaning of text from various document formats. The resulting system provides a streamlined and scalable solution for processing textual data, which can be valuable for applications such as data analysis, information retrieval, and natural language processing. By leveraging Amazon Textract for extraction and RapidMiner for cleaning, it provides a comprehensive solution for processing textual data. The extracted and cleaned text can be further utilized for various applications, such as data analysis, natural language processing, and information retrieval.<br /> <a href="https://github.com/prys0000/archives-textract"><strong>Explore the docs &raquo;</strong></a><br /> <br /> <a href="https://github.com/prys0000/archives-textract/issues">Report Bug</a></p>
<h4><strong>Table of Contents</strong></h4>
<ol>
<li><a href="#about-the-project">About The Project</a>
<ul>
<li><a href="#built-with">Built With</a></li>
</ul>
</li>
<li><a href="#getting-started">Getting Started</a>
<ul>
<li><a href="#prerequisites">Prerequisites</a></li>
<li><a href="#installation">Installation</a></li>
</ul>
</li>
<li><a href="#usage">Usage</a></li>
<li><a href="#roadmap">Roadmap</a></li>
<li><a href="#contributing">Contributing</a></li>
<li><a href="#license">License</a></li>
<li><a href="#contact">Contact</a></li>
<li><a href="#acknowledgments">Acknowledgments</a></li>
</ol>
<h2><strong>About The Project</strong></h2>
<p>The objective of this project is to develop a text extraction and cleaning tool that utilizes the capabilities of Amazon Textract and RapidMiner. The code extracts text from documents stored in an AWS S3 bucket, performs text cleaning operations using RapidMiner, and saves the extracted and cleaned text to Excel files. By automating the text extraction and cleaning processes, this project enables efficient handling of large-scale collections of documents. The use of Amazon Textract and RapidMiner allows for reliable and accurate extraction and cleaning of text from various document formats. The resulting system provides a streamlined and scalable solution for processing textual data, which can be valuable for applications such as data analysis, information retrieval, and natural language processing. By leveraging Amazon Textract for extraction and RapidMiner for cleaning, it provides a comprehensive solution for processing textual data. The extracted and cleaned text can be further utilized for various applications, such as data analysis, natural language processing, and information retrieval.`</p>
<p>(<a href="#readme-top">back to top</a>)</p>
<h2><strong>Built With</strong></h2>
<ul>
<li><a href="https://aws.amazon.com/textract/"><img src="https://hitconsultant.net/wp-content/uploads/2019/10/Amazon-Textract.jpg" alt="" width="100" height="50" /></a></li>
<li><a href="https://www.python.org/psf-landing/"><img src="https://i.redd.it/rxezjyf4ojx41.png" alt="" width="100" height="50" /></a></li>
<li><a href="https://rapidminer.com/platform/"><img src="https://rapidminer.com/wp-content/uploads/2022/04/Homepage-1.jpg" alt="" width="100" height="50" /></a></li>
<li><a href="https://getbootstrap.com/docs/3.4/javascript/"><img src="https://www.k2bindia.com/wp-content/uploads/2013/03/bootstrap-1.jpg" alt="" width="100" height="50" /></a></li>
</ul>
<p>(<a href="#readme-top">back to top</a>)</p>
<h2><strong>Getting Started</strong></h2>
<p>To get a local copy up and running follow these simple steps.</p>
<h3><strong>Prerequisites</strong></h3>
<p>There are steps required to run the archive-textract scripts. First you must install some system packages using the apt-get package manager before installing textract from pypi:</p>
<p>apt-get install python-dev libxml2-dev libxslt1-dev antiword unrtf poppler-utils pstotext tesseract-ocr \ flac ffmpeg lame libmad0 libsox-fmt-mp3 sox libjpeg-dev swig libpulse-dev pip install textract</p>
<h4><strong>Amazon AWS Cloudshell</strong></h4>
<ol>
<li>Create a session using your AWS credentials</li>
</ol>
<p style="padding-left: 60px;">session = boto3.Session</p>
<p style="padding-left: 60px;">aws_access_key_id=ACCESS KEY</p>
<p style="padding-left: 60px;">aws_secret_access_key=SECRET ACCESS KEY</p>
<p style="padding-left: 60px;">region_name=REGION</p>
<ol>
<li>If you are unable to install boto3 directly in AWS CloudShell, you can try using a virtual environment to install and run the package.</li>
</ol>
<p style="padding-left: 30px;"><strong>Step-by-step:</strong></p>
<p style="padding-left: 60px;">Open AWS CloudShell in your AWS Management Console.</p>
<p style="padding-left: 60px;">Create a virtual environment using the following command:</p>
<p style="padding-left: 60px;">Copy code python3 -m venv myenv</p>
<p style="padding-left: 60px;">Activate the virtual environment:&nbsp;</p>
<p style="padding-left: 60px;">Copy code source myenv/bin/activate</p>
<p style="padding-left: 60px;">Install boto3 using the pip command:</p>
<p style="padding-left: 60px;">Copy code pip install boto3 Once boto3 is installed, you can write and execute your code in the CloudShell terminal.</p>
<p style="padding-left: 30px;">Virtual environments in CloudShell are ephemeral and will be discarded when you close the session. You will need to repeat these steps each time you start a new CloudShell session.</p>
<p style="padding-left: 30px;"><strong>Once AWS is connected you will install a few basic packages:</strong></p>
<ol>
<li style="list-style-type: none;">
<ul style="list-style-type: disc;">
<li><strong>pyPDF2</strong>: This package is used for extracting text from PDF files.
<ul>
<li>You can install it using the command: pip install PyPDF2.</li>
</ul>
</li>
<li><strong>sumy:</strong> This package is used for text summarization.
<ul>
<li>You can install it using the command: pip install sumy.</li>
</ul>
</li>
<li><strong>openpyxl:</strong> This package is used for working with Excel files (.xlsx)
<ul>
<li>You can install it using the command: pip install openpyxl</li>
</ul>
</li>
<li><strong>rake-nltk:</strong> This package is used for keyword extraction algorithm which tries to determine key phrases in a body of text by analyzing the frequency of word appearance and its co-occurrence with other words in the text pyspellchecker: This package is is designed to be easy to use to get basic spell checking.
<ul>
<li>You can install it using the command: pip install rake-nltk</li>
</ul>
</li>
<li><strong>levenshtein:</strong> Levenshtein Python C extension module contains functions for fast computation of: Levenshtein (edit) distance, and edit operations, string similarity, approximate median strings, and generally string averaging
<ul>
<li>You can install it using the command: pip install levenshtein</li>
</ul>
<p>Once you have installed these packages make sure to provide the correct folder paths for the PDF files and the summary text files before executing the script</p>
<p>(<a href="#readme-top">back to top</a>)</p>
<h2>&nbsp;</h2>
</li>
</ul>
</li>
</ol>
<h2><strong>Usage</strong></h2>
<p>The archives-textract project has combined powerful Amazon AWS Textract services with automates the extraction of text and data from scanned documents. It goes beyond traditional OCR by not only recognizing printed text but also identifying and extracting information from historical handwritten documents, enabling efficient digitization and preservation of valuable records. Textract can be leveraged for indexing documents, creating subject or topic classifications based on the extracted handwritten text, allowing for efficient organization and retrieval of information from large document collections.</p>
<p>Using Python, we have created a workflow that automatically retrieves documents from a designated source, passes them through the Textract service for text extraction (including handwritten text), and stores the extracted information in an organized manner allowing for migration, long-term data preservation, and access to large data stores for collection analysis. Scripting enables the integration of additional functionalities such as sentiment analysis, indexing, and topic creation. This automation significantly reduces the manual efforts required for archival processing, saving time and increasing efficiency.</p>
<p>When extracting handwritten text, it's important to note that the accuracy and reliability of extracting handwritten text can vary depending on the legibility of the handwriting itself. Handwritten text presents a unique challenge due to variations in handwriting styles, quality, and clarity. In cases where the handwritten text is not clearly written or is difficult to interpret, the accuracy of the extracted text may be compromised. Textract relies on machine learning algorithms to analyze and recognize text, but it may struggle with handwritten text that is messy, overlapping, or illegible.</p>
<p>Several packages have been used to increase readability including Levenshtein which has proven to create the most reliable reults: The accuracy algorithm used is based on the fuzzywuzzy library, which implements the Levenshtein distance algorithm for fuzzy string matching. The specific algorithm used is the token sort ratio. The token sort ratio is a variation of the standard Levenshtein distance algorithm that takes into account the order of the words in the compared strings. It first tokenizes the strings into individual words, sorts them alphabetically, and then compares the sorted tokens. This approach is useful when comparing text that may have different word order but still represent the same information. The resulting similarity score from the token sort ratio algorithm represents the percentage of similarity between the two strings. A score of 100 indicates an exact match, while lower scores indicate a decreasing level of similarity. In the provided code, a similarity threshold is set to 70. This means that only text pairs with a similarity score equal to or above 70 will be considered as a match. Any pairs below this threshold will have an accuracy of 0. You can adjust the similarity threshold value according to your specific needs and the level of strictness you want for considering a match. Higher values will require a closer match, while lower values will allow for more leniency. It's important to note that while the token sort ratio algorithm can provide a good indication of similarity, it may not always capture the full context or meaning of the text. You may need to consider additional techniques or algorithms depending on the specific requirements of your application.</p>
<p>For more examples, please refer to the [LINK DOC](https://example.com)_</p>
<p>(<a href="#readme-top">back to top</a>)</p>
<h3><strong>Contributing</strong></h3>
<p>Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**. If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement". Don't forget to give the project a star! Thanks again!</p>
<p>(<a href="#readme-top">back to top</a>)</p>
<h3><strong>License</strong></h3>
<p>Distributed by the Carl Albert Congressional Center Archives. See `LICENSE.txt` for more information.</p>
<p>(<a href="#readme-top">back to top</a>)</p>
<h3><strong>Contact</strong></h3>
<p>JA Pryse - japryse@ou.edu</p>
<p>Project Link: <a href="https://github.com/prys0000/archives-textract](https://github.com/prys0000/archives-textract">https://github.com/prys0000/archives-textract](https://github.com/prys0000/archives-textract</a>&nbsp;</p>
<p>(<a href="#readme-top">back to top</a>)</p>
<h3><strong>Acknowledgments</strong></h3>
<p>* []() * []() * []()</p>
<p>(<a href="#readme-top">back to top</a>)</p>
