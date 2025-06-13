# MM-TKGF
Appendix of paper： When multi-modal meets temporal knowledge graph: A new perspective for temporal knowledge graph 

## Baseline link

### Static Methods

DistMult: https://github.com/thunlp/OpenKE

ConvE: https://github.com/TimDettmers/ConvE

RotatE: https://github.com/DeepGraphLearning/KnowledgeGraphEmbedding

AnyBURL：https://web.informatik.uni-mannheim.de/AnyBURL

### Multi-modal Methods

TransAE： https://github.com/ksolaiman/TransAE

NativE：https://github.com/zjukg/NATIVE

SNAG：https://github.com/zjukg/SNAG

IKRL:https://github.com/thunlp/IKRL

MKGFormer: https://github.com/zjunlp/MKGformer

SMPGT: Since the offical code for SGMPT is not publicly available, their idea and intentions described in the paper can be achieved simply modifying MKGFormer (list above). By adding a static KG embedding method (HAKE is recommend in the paper), and perform a weight sum ($\lambda_{s}^{ts}$ and $\lambda_{s}^{is}$ of its structural embeddings. Then, in the loss function, add MSE losses with weight $\lambda_{a}^{ts}$ and $\lambda_{a}^{is}$ repectively to use the structural embeddings to constrain the multi-modal (textual, and image) features.

### Uni-modal Temporal Methods

CyGNet: https://github.com/CunchaoZ/CyGNet

TANGO: https://github.com/temporalkgteam/tango

Know-Evolve: https://github.com/rstriv/Know-Evolve

EvoKG: https://github.com/NamyongPark/EvoKG

CEN: https://github.com/lee-zix/cen

STDN: https://dl.acm.org/doi/suppl/10.1145/3648366/suppl_file/tkdd-2023-07-0300-file002.zip

TiRGN: https://github.com/Liyyy2122/TiRGN

CENET: https://github.com/xyjigsaw/CENET

Re-Temp: https://github.com/adlnlp/re-temp

PLEASING: https://github.com/KcAcoZhang/PLEASING

LogCL: https://github.com/WeiChen3690/LogCL


## Dataset link
The dataset is available at One Drive Disk https://1drv.ms/f/c/32f7834191744307/QgdDdJFBg_cggDIGDgAAAAAAvDXmCeK0mBOFng

### Folder Structure

```
MMTKGF # root folder
 |-- MMICEWSxx	# xx represents year
 |    |-- textual       # textual information
 |    |    |-- QXXXXXX.json # XXXXXXX represents entity code, includes names, attributes and descriptions
 |    |    |-- ...
 |    |-- images          # image information
 |    |    |-- QXXXXXX #XXXXXXX represents entity code
 |    |    |    |-- xxxxx.jpg (png, or svg) # raw images
 |    |    |    |-- ...
 |    |    |-- ...
 |    |-- data    # strcutrual data
 |    |    |-- ICEWSXX.tab # icews data
 |    |    |-- entity_reflection.csv # align icews entity to wikidata entity
 
```
