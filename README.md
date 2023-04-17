# A Survey on Automatic Generation of Figurative Language: From Rule-based Systems to Large Language Models

<h2 id="0">Abstract</h2>

<tr>
Figurative language generation (FLG) is the task of reformulating a given text to include a desired figure of speech, 
such as a hyperbole, a simile, and several others, while still being faithful to the original context. This is a fundamental, 
yet challenging task in Natural Language Processing (NLP) to achieve ever more natural text generation, 
which has recently received increased attention due to the promising performance brought by pre-trained language models. 
Our survey provides a systematic overview of the development of FLG, mostly in English, starting with the description of some common figures of speech, 
their corresponding generation tasks and datasets. We then focus on various modelling approaches and assessment strategies, 
leading us to discussing some challenges in this field, and suggesting some potential directions for future research. 
To the best of our knowledge, this is the first survey that summarizes the progress of FLG including the most recent development in NLP. 
We also organize corresponding resources, e.g., paper lists and datasets, and make them accessible in an open repository. 
We hope this survey can help researchers in NLP and related fields to easily track the academic frontier, providing them with a landscape and a roadmap of this area.
</tr>

<h2 id="1">Survey Overview</h2>

![](./img/overview.png)

<h2 id="2">Datasets & Benchmarks</h2>

<table>
  <tr>
    <th align="center">Figure of speech</th>
    <th align="center">Task</th>
    <th align="center">Dataset</th>
    <th align="center">train</th>
    <th align="center">Valid</th>
    <th align="center">Test</th>
    <th align="center">Lang</th>
    <th align="center">Para</th>
  </tr >

  <tr>
    <th rowspan="4" align="center" valign="middle">Simile</th>
    <td align="center">Literal&harr;Simile</td>
    <td align="center"> <a href="https://github.com/tuhinjubcse/SimileGeneration-EMNLP2020">Data</a> </td>
    <td align="center">82,687</td>
    <td align="center">5,145</td>
    <td align="center">150</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center">Simile↔Context</td>
    <td align="center"> <a href="https://github.com/mrzjy/writing-polishment-with-simile">Data</a> </td>
    <td align="center">5.4M</td>
    <td align="center">2,500</td>
    <td align="center">2,500</td>
    <td align="center">zh</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center">Narrative+Simile→Text</td>
    <td align="center"> <a href="https://github.com/tuhinjubcse/FigurativeNarrativeBenchmark">Data</a> </td>
    <td align="center">3,100</td>
    <td align="center">376</td>
    <td align="center">1,520</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center">Concept→Analogy + Explanation</td>
    <td align="center"> <a href="https://github.com/Bhaavya/InstructGPT-Analogies">Data</a> </td>
    <td align="center">-</td>
    <td align="center">-</td>
    <td align="center">148</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>

  <tr>
    <th rowspan="5" align="center" valign="middle">Metaphor</th>
    <td rowspan="5" align="center">Literal&harr;Metaphor</td>
    <td align="center"> <a href="https://github.com/UKPLab/conll2021-metaphoric-paraphrase-generation">Data</a> </td>
    <td align="center">260k</td>
    <td align="center">15,833</td>
    <td align="center">250</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center"> <a href="https://github.com/tuhinjubcse/MetaphorGenNAACL2021">Data</a> </td>
    <td align="center">90k</td>
    <td align="center">3,498</td>
    <td align="center">150</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center"> <a href="https://github.com/UKPLab/acl2021-metaphor-generation-conceptual">Data</a> </td>
    <td align="center">248k</td>
    <td align="center">-</td>
    <td align="center">150</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center"> <a href="http://saifmohammad.com/WebPages/metaphor.html">Data</a> </td>
    <td align="center">-</td>
    <td align="center">-</td>
    <td align="center">171</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center"> <a href="https://github.com/liyucheng09/Metaphor_Generator">CMC</a> </td>
    <td align="center">3,554/2,703</td>
    <td align="center">-</td>
    <td align="center">-</td>
    <td align="center">zh</td>
    <td align="center">&#10007</td>
  </tr>

  <tr>
    <th rowspan="4" align="center" valign="middle">Hyperbole</th>
    <td rowspan="4" align="center">Literal&harr;Hyperbole</td>
    <td align="center"> <a href="https://aclanthology.org/D18-1367/">Paper</a> </td>
    <td align="center">709</td>
    <td align="center">-</td>
    <td align="center">-</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center"> <a href="http://lichuanyi.info/paper/chinese_hypo.txt">HYPO-cn</a> </td>
    <td align="center">2,082/2,680</td>
    <td align="center">-</td>
    <td align="center">-</td>
    <td align="center">zh</td>
    <td align="center">&#10007</td>
  </tr>
  <tr>
    <td align="center"> <a href="https://github.com/NinaTian98369/HypoGen">HYPO-red</a> </td>
    <td align="center">2,163/1,167</td>
    <td align="center">-</td>
    <td align="center">-</td>
    <td align="center">en</td>
    <td align="center">&#10007</td>
  </tr>
  <tr>
    <td align="center"> <a href="https://github.com/yunx-z/MOVER">HYPO-XL</a> </td>
    <td align="center">-/17,862</td>
    <td align="center">-</td>
    <td align="center">-</td>
    <td align="center">en</td>
    <td align="center">&#10007</td>
  </tr>

  <tr>
    <th rowspan="5" align="center" valign="middle">Idiom</th>
    <td align="center">Idiom&harr;Literal</td>
    <td align="center"> <a href="https://aclanthology.org/N16-1040/">Paper</a> </td>
    <td align="center">88</td>
    <td align="center">-</td>
    <td align="center">84</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center">Idiom (en)↔Literal (de)</td>
    <td rowspan="2" align="center"> <a href="https://github.com/marziehf/IdiomTranslationDS">Data</a> </td>
    <td align="center">1,998</td>
    <td align="center">-</td>
    <td align="center">1,500</td>
    <td align="center">en/de</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center">Idiom (de)↔Literal (en)</td>
    <td align="center">1,848</td>
    <td align="center">-</td>
    <td align="center">1,500</td>
    <td align="center">de/en</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center">Literal↔Idiom</td>
    <td align="center"> <a href="https://github.com/zhjjn/PIE">PIE</a> </td>
    <td align="center">3,784</td>
    <td align="center">876</td>
    <td align="center">876</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center">Narrative+Idiom→Text</td>
    <td align="center"> <a href="https://github.com/tuhinjubcse/FigurativeNarrativeBenchmark">Data</a> </td>
    <td align="center">3,204</td>
    <td align="center">355</td>
    <td align="center">1,542</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>

  <tr>
    <th rowspan="4" align="center" valign="middle">Irony (Sarcasm)</th>
    <td rowspan="4" align="center">Literal&harr;Irony (Sarcasm)</td>
    <td align="center"> <a href="https://github.com/Lotemp/SarcasmSIGN">Data</a> </td>
    <td align="center">2,400</td>
    <td align="center">300</td>
    <td align="center">300</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center"> <a href="https://github.com/TarunTater/sarcasm_generation">Data</a> </td>
    <td align="center">-</td>
    <td align="center">-</td>
    <td align="center">203</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center"> <a href="https://github.com/zmd971202/IronyGeneration">Data</a> </td>
    <td align="center">112k/262k</td>
    <td align="center">-</td>
    <td align="center">-</td>
    <td align="center">en</td>
    <td align="center">&#10007</td>
  </tr>
  <tr>
    <td align="center"> <a href="https://github.com/debanjanghosh/interpreting_verbal_irony">Data</a> </td>
    <td align="center">4,762</td>
    <td align="center">-</td>
    <td align="center">-</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>

  <tr>
    <th rowspan="2" align="center" valign="middle">Pun</th>
    <td align="center">Word senses→Pun</td>
    <td align="center"> <a href="https://www.informatik.tu-darmstadt.de/ukp/research_ukp/ukp_research_data_and_software/ukp_data_and_software.en.jsp">Data</a> </td>
    <td align="center">1,274</td>
    <td align="center">-</td>
    <td align="center">-</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>
  <tr>
    <td align="center">Context→Pun</td>
    <td align="center"> <a href="https://github.com/amazon-science/context-situated-pun-generation">Data</a> </td>
    <td align="center">2,753</td>
    <td align="center">-</td>
    <td align="center">-</td>
    <td align="center">en</td>
    <td align="center">&#10003</td>
  </tr>
  
  <tr>
    <th rowspan="2" align="center" valign="middle">Personification </th>
    <td align="center">Topic→Personification</td>
    <td align="center"> <a href="https://github.com/Lucien-qiang/Rhetoric-Generator">Data</a> </td>
    <td align="center">67,441</td>
    <td align="center">3,747</td>
    <td align="center">3,747</td>
    <td align="center">zh</td>
    <td align="center">&#10003</td>
  </tr>
</table>


