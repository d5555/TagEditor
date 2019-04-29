### TagEditor(v1.5.2) annotation tool

TagEditor is a desktop application (tested on _Windows 10, 64-bit_) designed to annotate text for training with spaCy library.<br/>
With TagEditor you can label **dependencies, parts of speech, Named entities, text categories and Coreference resolution**.

### Installation
No installation required.
Download and unpack(extract) [**TagEditorSFX.exe**](https://github.com/d5555/TagEditor/raw/master/TagEditorSFX.exe)<br/>
Launch shortcut TagEditor.exe <br/>

### Usage

![alt text](https://github.com/d5555/TagEditor/blob/master/pics/dep800.gif)

&nbsp; Insert your text or open a text file and press Start tagging (or choose one of the options in Menu/Tools). Choose types of annotation and labels like in the screenshot below and press Ok. <br/>
![alt text](https://github.com/d5555/TagEditor/blob/master/pics/select.png)<br/>
Select a tag in TAG SET pannel then select a word to assign the tag. Select a head tag to assign dependency if you are working in the Dependencies window .<br/>
&nbsp; Right-click on a word to edit, delete, insert word, merge or split sentences. 
To merge sentences right-click on the first word of sentence. It is checked as **Sentence start**. Uncheck it and the sentence will merge with the previous sentence. <br/>
&nbsp; To delete all newline characters and extra whitespaces in the text, select the tab **Words** and press **Remove Whitespaces**.<br/> 
Press button **Create DATA** to create data in "simple training style" or JSON.<br/>
**Save project** for future editing. **Load project** to continue where you left.

**Co-reference tagger**<br/>
&nbsp;Coreference annotation is according to PreCo  'Data Format'.<br/>Compatible with **NeuralCoref 4.0**. To use NeuralCoref for annotating select "Enable NeuralCoref" after 'Start tagging'. Set parameter 'greedyness' 0,55.

https://arxiv.org/abs/1810.09807<br/>
https://preschool-lab.github.io/PreCo/<br/>
"sentences" - is a list of sentences. Each sentence is a list of tokens. Each token is a string, which can be a word or a punctuation mark. <br/>
"mention_clusters" - is a list of mention clusters. Each mention cluster is a list of mentions. Each mention is a tuple of integers [sentence_idx, begin_idx, end_idx]. Sentence_idx is the index of the sentence of the mention. Begin_idx is the index of the first token of the mention in the sentence. End_index is the index of the last token of the mention in the sentence plus one. All indices are zero-based.<br/>
&nbsp;&nbsp;Select a word or a span of words. It will be a singleton(single entity) with no connection to other entities and framed with dash line. Then select another span. Everytime you select an entity it is highlighted by green color frame. While it is in selected state click on another entity and they will be linked together and highligted by same color and get same coref number (a num in the right corner of frame). That simple! <br/>
To deselect just click on empty space in the main window.<br/>
To unlink a span from the entity , select it and then click on it again. It will turn into singleton. You can also use the table on the right side. If the text is long and you don't want to scroll it just click on an entity in the table to get spans linked. Entities which are not singletons are added to the table automatically. Though you can add singletons too. Entity color can be changed except for singleton. <br/>
![alt text](https://github.com/d5555/TagEditor/blob/master/pics/corefpic.png)
![alt text](https://github.com/d5555/TagEditor/blob/master/pics/coref_annot.png)

**Dependencies**<br/>
Select a tag in TAG SET pannel then select a word to assign the tag. Click on another word(token) to assign a head tag.
![alt text](https://github.com/d5555/TagEditor/blob/master/pics/dep.png)

**How to use Text Categories**<br/>
In the Text Categories you can assign labels to sentences (default mode) or to spans (see below).<br/>
&nbsp; Select the score in the TAG SET pannel - True or False(i.e 1.0 or 0.0) and select a category label. Go to the editor window and click on sentence. Category and score will be added. You can easily **switch the score True/False** by just clicking on the score label in editor window. Supports multiple, non-mutually exclusive labels.<br/>
Use check button **Assign/unassign all** to assign/unassign all labels to all sentences in one click. Then you can manually change True/False status of each label or delete a label in the editor window.<br/>
For demo purporses the text classifier of this tool was trained on the IMDB dataset with labels 'POSITIVE NEGATIVE'<br/>
https://spacy.io/usage/training#textcat<br/>
![alt text](https://github.com/d5555/TagEditor/blob/master/pics/cats.png)
'Spans classification mode' allows **multiple intercrossing labels**.  Can be used as an **all-purporse text tagger** with the data format (index of first token, index of last token+1, label name). Zero based.<br/>
![alt text](https://github.com/d5555/TagEditor/blob/master/pics/spansclass.png)

**Named Entities**<br/>
First click on a label in the Tag Set pannel then select text in the main window. To delete assigned label from text just click on it.
![alt text](https://github.com/d5555/TagEditor/blob/master/pics/ner.png)
**POS tags**<br/>
![alt text](https://github.com/d5555/TagEditor/blob/master/pics/pos_pic.png)
<!---**************
### Extended version
Need help, found a bug or you would like get the extended version? [**New issue**](https://github.com/d5555/TagEditor/issues/new) or contact us at gitprojects5@gmail.com
**************
gitprojects5@gmail.com 


[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://paypal.me/d5555)<br/>--->
