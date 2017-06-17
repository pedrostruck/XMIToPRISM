# Astah-XMI-UnB-DALi
Astah UML XMI files transformed to DTMC via UnB-DALi

This project is to attempt to extract the information of an UML diagram in the form of an XMI file so that it can be used as input to the UnB-Dependability Analisys Library, that conducts the graph transformation of a UML diagram to a Discrete Time Markov Chain (DTMC) in the language of the PRISM model checker tool.

# How to insert probabilities in your Astah Diagram
We assume that the user is familiar with the Astah UML tool.

## Activity Diagrams
To annotate the probability in your transitions, select an edge and insert a real number n in the "Weight" field, in the "Base" parameters of the edge, where 0.0 <= n <= 1.0.

##Sequence Diagrams
To annotate the probability in your components (lifelines), select the lilfeline and click on the tab "TaggedValue". Click on "Add" and put a name (suggestion "prob" or "p", from "probability", but it can be any name) and a value n, where 0.0 <= n <= 1.0.

# How to use the transformation tool
To conduct the transformation, we assume that you have your UML model/project ready on the Astah Professional tool, properly annotated with the probabilities.

Follow these steps:

1- Inside Astah Professional, with your opened project, click on Tools > XML Input & Output > Save as XML Project

2- Go to the folder where the project is and copy the generated XML file

3- Open the astah-xmi-unbdali project on Eclipse

4- Paste your XML file inside the "xmi-files" folder

5- Open the MainClass on the br.unb.xmiimport package

6- Execute the program

7- Insert the name of your file on the console (without the .xml extension) and press enter

8- The result in PRISM language is in text form on the console, starting with "dtmc" and ending with "endmodule". A file with the same name as the XML input file is generated with a ".pm" extension inside the "output" folder. If the original diagram is well-constructed, the <filename>.pm is a PRISM compilable file.
In case you don't see the output file, refresh the project (hotkey: F5).