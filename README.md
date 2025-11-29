# MM-TKGF
Appendix of paper： When multi-modal meets temporal knowledge graph: A new perspective for temporal knowledge graph forecasting

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

SGMPT: 
(1) First, we use the MKGFormer as backbone model, as noted in SGMPT, Section 3.2 (Liang et al. (2024)).

(2) Next, we leverage a static KG embedding method HAKE as a structural encoder, as noted in SGMPT, Section 3.3.1.

(3) Then, we create a structure-guided fusion module, which aims to fuse each modality via a weighted sum. For textual features, we scale the structural embeddings with a weight \lambda_s^{ts}=0.01(as noted in SGMPT, Section 4.1.2) and adds them to the text embeddings. Similarly, for image features, we scale the augmented structural embeddings with a weight \lambda_s^{vs}=0.01 (as referenced in SGMPT, Section 4.1.2), and add them to the image embeddings.

(4) After that, we add an alignment constraint by using MSE losses with weights \lambda_a^{ts}= 0.001 and \lambda_a^{vs}=\ 0.001 respectively to constrain multi-modal (textual, and image) features. 

(5) Finally, we utilize the above-mentioned alignment constraint loss with binary cross entropy loss as the final objective function (as noted in SGMPT, Section 3.3.2), and use the hyper-parameter setting recommended in the SGMPT to run the model: \mathcal{L}=\mathcal{L}_{ce}+\mathcal{L}_a

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

## Dataset construction process

### Image features
Entities corresponding to Wikidata property image (P18), locator map image (P242), flag image (P41), coat of arms image (P94), seal image (P158), page banner (P948), aerial view (P8592), location map (P1943), spherical panorama image (P4640), related image (P6802), reference image (P10253), image of interior (P5775), plaque image (P1801), signature (P109), non-free artwork image URL (P6500), montage image (P2716), image of back side (P7417), service ribbon image (P2425), image of design plans (P3311), image of entrance (P9721), inscription image (P9906), model image (P11101), winter view (P5252), image of grave (P1442), image with color chart (P10093), escutcheon image (P4004), bathymetry image (P207), image of front side (P7418), code (image) (P7415), route map (P15), image with frame (P7420), view (P8517), logo image (P154), icon (P2910), source of file (P7482), monogram (P1543), taxon range map image (P181), signature (P109), Gene Atlas image (P692), and distribution map (P1846) are extracted as sources.

### Textual features
Entities description are obtained through the class “wikibase-entitytermsview-heading-description”. In cases where textual features contain non-standard Latin letters, we transliterate them into standard Latin letters.

## Dataset link
The dataset is available at One Drive Disk https://1drv.ms/f/c/32f7834191744307/EgdDdJFBg_cggDIGDgAAAAABrHIZu_4Px63KjclnRTddVQ?e=qUCNUa

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
* Mapping table entity_reflection.csv can be restored from id and name fields of the corresponding entities in the textual folder.
