### TagEditor(v3.0.5) annotation tool

TagEditor is a desktop application (requires **_Windows 10, 64-bit_**) designed to annotate text for training with spaCy library.<br/>
With TagEditor you can label **dependencies, parts of speech, Named entities, text categories and Coreference resolution** or create your customized training data.

### Installation
No installation required.<br/>
Download and unpack [**TagEditor.7z**](https://github.com/d5555/TagEditor/raw/master/TagEditor.7z)<br/>
Run 'TagEditor.exe' in the main folder.

### Demo

![alt text](https://github.com/d5555/TagEditor/blob/master/pics/dep800.gif)

### Usage

&nbsp; Insert your text or open a text file and press **Start tagging** (or choose one of the options in Menu/Tools). Choose type of annotation and labels like in the screenshot below and press Ok. Or you can start with loading your datasets in formats .spacy (spaCy v3) or .json (spacy v2).

![alt text](https://github.com/d5555/TagEditor/blob/master/pics/select.png)<br/>
Select a tag in **TAG SET pannel** then select a word to assign the tag. Select a head tag to assign dependency if you are working in the Dependencies window .<br/>
&nbsp; To edit Doc or Tokens  - use Right-click on any word. It allows to  edit, delete, insert words or sentences, also merge or split sentences. 
To merge sentences right-click on the first word of sentence. It is checked as **Sentence start**. Uncheck it and the sentence will merge with the previous sentence.<br/> 
<img src="https://github.com/d5555/TagEditor/blob/master/pics/Context.png" width="700" >

&nbsp; To assign new paragraph use context menu or click on the sentence number on the left side. Or use button **Assign paragraphs** in the tab **Words** to assign paragraphs after new line symbols '\n' in text. <br/>
&nbsp; To delete all newline characters and extra whitespaces in the text, select the tab **Words** and press **Remove Whitespaces**.<br/> 
<!---![alt text](https://github.com/d5555/TagEditor/blob/master/pics/words.png)--->
<img src="https://github.com/d5555/TagEditor/blob/master/pics/words.png" width="700" >

Press button **Create DATA** to create training data in "simple training style" or JSON. You can save it in text, json or spacy format ...<br/>
**Save project** for future editing. **Load project** to continue where you left.<br/>
Also you can load your datasets in formats .spacy (spaCy v3) or .json (spaCy v2). 

<img src="https://github.com/d5555/TagEditor/blob/master/pics/MenuFile.png" width="700" >

If you don't have a pretrained model for a given language, select the language from list for proper tokenization: 

<img src="https://github.com/d5555/TagEditor/blob/master/pics/Menu_Mod.png" width="450" >

<!--- >Try **[NeuralGym](https://github.com/d5555/NeuralGym)** to train spaCy model with your training data. --->

**Named Entities**<br/>
First click on a label in the Tag Set pannel then select text in the main window. To delete assigned label from text just click on it. Create output data with char/token offset or BILUO / IOB scheme. It is allowed to create nested or overlapping tags if you use char/token offset.<br/>
Option **--annotate--** allows to switch models and overwrite existing labels in different modes. 

![alt text](https://github.com/d5555/TagEditor/blob/master/pics/ner1.png) 


Press button **Create data** , select items and save as **\*.spacy, \*.txt or \*.json** format or print it on the screen. if you assigned paragraphs - select **Manually assigned paragraphs**<br/>
<!--- ![alt text](https://github.com/d5555/TagEditor/blob/master/pics/create_data.png width=400) --->
<img src="https://github.com/d5555/TagEditor/blob/master/pics/create_data.png" width="450" >

![alt text](https://github.com/d5555/TagEditor/blob/master/pics/data_onscreen.png)

**POS tags**<br/>
In this window you can edit POS tags (fine-grained) and also view coarse-grained pos tags and morphs.<br/>
![alt text](https://github.com/d5555/TagEditor/blob/master/pics/pos_pic.png)

**Dependencies**<br/>
Select a tag in TAG SET pannel then click on a word in the editor window to assign the tag. Click on another word(token) to assign a head tag. Click on the word again to remove the tag.
![alt text](https://github.com/d5555/TagEditor/blob/master/pics/dep.png)

**Co-reference tagger**<br/>
&nbsp;Coreference annotation is according to PreCo  'Data Format'.<br/>Dataset can be downloaded from here: https://github.com/d5555/Coreference-dataset<br/>Compatible with **NeuralCoref 4.0**. To use NeuralCoref for annotating select "Enable NeuralCoref" after 'Start tagging'. Set parameter 'greedyness' 0,55.

https://preschool-lab.github.io/PreCo/<br/>
https://arxiv.org/abs/1810.09807<br/>
"sentences" - is a list of sentences. Each sentence is a list of tokens. Each token is a string, which can be a word or a punctuation mark. <br/>
"mention_clusters" - is a list of mention clusters. Each mention cluster is a list of mentions. Each mention is a tuple of integers [sentence_idx, begin_idx, end_idx]. Sentence_idx is the index of the sentence of the mention. Begin_idx is the index of the first token of the mention in the sentence. End_index is the index of the last token of the mention in the sentence plus one. All indices are zero-based.<br/>
&nbsp;&nbsp;Select in the editor window a word or a span of words. It will be a singleton(single entity) with no connection to other entities and framed with dash line. Then select another span. Everytime you select an entity it is highlighted by green color frame. While it is in selected state click on another entity and they will be linked together and highligted by same color and get same coref number (a num in the right corner of frame). That simple! <br/>
To deselect just click on empty space in the main window.<br/>
To unlink a span from the entity , select it and then click on it again. It will turn into singleton. You can also use the table on the right side. If the text is long and you don't want to scroll it just click on an entity in the table to get spans linked. Entities which are not singletons are added to the table automatically. Though you can add singletons too. Entity color can be changed except for singleton. <br/>
You can load data from PreCo dataset to TagEditor directly. Unzip  PreCo dataset , run tagEditor and select menu **File->Load PreCO/Coref->(select file)**. You can test it with the file **coref_example.jsonl** <br/>
![alt text](https://github.com/d5555/TagEditor/blob/master/pics/corefpic.png)
![alt text](https://github.com/d5555/TagEditor/blob/master/pics/coref_annot.png)

**Text Categories**<br/>
In the Text Categories you can assign labels to paragraphs, sentences or to spans (see below).<br/>
&nbsp; Select the score in the TAG SET pannel - True or False(i.e 1.0 or 0.0) and select a category label. Go to the editor window and click on sentence. Category and score will be added. You can easily **switch the score True/False** by just clicking on the score label in editor window. Supports multiple, non-mutually exclusive labels.<br/>
Use check button **Assign/unassign all** to assign/unassign all labels to all sentences in one click. Then you can manually change True/False status of each label by clicking on the label or delete the label in the editor window.<br/>
For demo purporses the text classifier of this tool was trained on the IMDB dataset with labels 'POSITIVE NEGATIVE'<br/>
https://spacy.io/api/textcategorizer<br/>
![alt text](https://github.com/d5555/TagEditor/blob/master/pics/cats.png)
![alt text](https://github.com/d5555/TagEditor/blob/master/pics/cat_data.png)

'Spans classification mode' allows **multiple overlapping labels**.  Can be used as an **all-purporse text tagger** with the data format (index of first token, index of last token+1, label name). Zero based.<br/>
<!---![alt text](https://github.com/d5555/TagEditor/blob/master/pics/spansclass.png) --->
<img src="https://github.com/d5555/TagEditor/blob/master/pics/spansclass.png" width="700" >

<!--- _Try **[NeuralGym](https://github.com/d5555/NeuralGym)** to train spaCy model with your training data._ <br/>  --->
>To use your pretrained models with TagEditor or other spacy models,  acquire the full version of TagEditor. Please contact gitprojects5@gmail.com 
#### *You have any suggestions on improving the program, adding extra feature, feel free to leave a comment or email at gitprojects5@gmail.com
<!---**************
### Extended version
Need help, found a bug or you would like get the extended version? [**New issue**](https://github.com/d5555/TagEditor/issues/new) or contact us at gitprojects5@gmail.com
**************
gitprojects5@gmail.com 


[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://paypal.me/d5555)<br/>--->
