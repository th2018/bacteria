bacteria
================
Ilya
12/7/2018

#### install packages

#### read in data from Brbic et al. (ProTraits: <http://protraits.irb.hr/data.html>)

``` r
PT = fread("ProTraits_precisionScores.txt",blank.lines.skip=TRUE)
# PT[1,]
unique(PT$Phenotype)
```

    ##   [1] "alkaline_phosphatase"                                            
    ##   [2] "arbutin"                                                         
    ##   [3] "cellobiose"                                                      
    ##   [4] "d-arabinose"                                                     
    ##   [5] "d-galacturonate"                                                 
    ##   [6] "d-glucuronate"                                                   
    ##   [7] "d-malic_acid"                                                    
    ##   [8] "d-xylose"                                                        
    ##   [9] "esterase_lipase__c8"                                             
    ##  [10] "esterase__c4"                                                    
    ##  [11] "fructose"                                                        
    ##  [12] "g-amino-butyric_acid"                                            
    ##  [13] "gelatin_hydrolysis"                                              
    ##  [14] "glutamate"                                                       
    ##  [15] "glycerol"                                                        
    ##  [16] "glycogen"                                                        
    ##  [17] "hydrogen_sulfide"                                                
    ##  [18] "lactate"                                                         
    ##  [19] "lactose"                                                         
    ##  [20] "mannitol"                                                        
    ##  [21] "melibiose"                                                       
    ##  [22] "n-acetyl-neuraminic_acid"                                        
    ##  [23] "n-acetylglucosamine"                                             
    ##  [24] "quinic_acid"                                                     
    ##  [25] "sorbitol"                                                        
    ##  [26] "starch"                                                          
    ##  [27] "sucrose"                                                         
    ##  [28] "beta-glucosidase"                                                
    ##  [29] "catalase"                                                        
    ##  [30] "d-arabitol"                                                      
    ##  [31] "dextrin"                                                         
    ##  [32] "formate"                                                         
    ##  [33] "inosine"                                                         
    ##  [34] "malate"                                                          
    ##  [35] "raffinose"                                                       
    ##  [36] "trehalose"                                                       
    ##  [37] "urease"                                                          
    ##  [38] "alpha-glucosidase"                                               
    ##  [39] "alpha-ketoglutaric_acid"                                         
    ##  [40] "alanine"                                                         
    ##  [41] "d-saccharate"                                                    
    ##  [42] "gentiobiose"                                                     
    ##  [43] "gluconate"                                                       
    ##  [44] "l-arabinose"                                                     
    ##  [45] "l-rhamnose"                                                      
    ##  [46] "nitrate_reduction"                                               
    ##  [47] "salicin"                                                         
    ##  [48] "acetate"                                                         
    ##  [49] "maltose"                                                         
    ##  [50] "propionate"                                                      
    ##  [51] "cystine_arylamidase"                                             
    ##  [52] "indole_production"                                               
    ##  [53] "lipase__c14"                                                     
    ##  [54] "myo-inositol"                                                    
    ##  [55] "n-acetyl-b-d-mannosamine"                                        
    ##  [56] "turanose"                                                        
    ##  [57] "valine_arylamidase"                                              
    ##  [58] "beta-galactosidase"                                              
    ##  [59] "2-ketogluconate"                                                 
    ##  [60] "adipate"                                                         
    ##  [61] "aesculin"                                                        
    ##  [62] "amygdalin"                                                       
    ##  [63] "arginine_dihydrolase"                                            
    ##  [64] "aspartate"                                                       
    ##  [65] "benzoate"                                                        
    ##  [66] "casein"                                                          
    ##  [67] "chymotrypsin"                                                    
    ##  [68] "citrate"                                                         
    ##  [69] "d-aspartic_acid"                                                 
    ##  [70] "d-lyxose"                                                        
    ##  [71] "ethanol"                                                         
    ##  [72] "fructose-6-phosphate"                                            
    ##  [73] "glucose-6-phosphate"                                             
    ##  [74] "glucose"                                                         
    ##  [75] "glycine"                                                         
    ##  [76] "hippurate"                                                       
    ##  [77] "histidine"                                                       
    ##  [78] "l-arabitol"                                                      
    ##  [79] "l-arginine"                                                      
    ##  [80] "l-pyroglutamic_acid"                                             
    ##  [81] "l-sorbose"                                                       
    ##  [82] "leucine"                                                         
    ##  [83] "mannose"                                                         
    ##  [84] "methyl_beta-d-glucopyranoside"                                   
    ##  [85] "methyl_beta-d-xylopyranoside"                                    
    ##  [86] "mucic_acid"                                                      
    ##  [87] "n-acetyl-beta-glucosaminidase"                                   
    ##  [88] "oxidase"                                                         
    ##  [89] "phenylacetate"                                                   
    ##  [90] "serine"                                                          
    ##  [91] "tagatose"                                                        
    ##  [92] "trypsin"                                                         
    ##  [93] "alpha-fucosidase"                                                
    ##  [94] "alpha-galactosidase"                                             
    ##  [95] "alpha-hydroxybutyric_acid"                                       
    ##  [96] "galactose"                                                       
    ##  [97] "l-fucose"                                                        
    ##  [98] "melezitose"                                                      
    ##  [99] "naphthol-as-bi-phosphohydrolase"                                 
    ## [100] "pyruvate"                                                        
    ## [101] "ribose"                                                          
    ## [102] "stachyose"                                                       
    ## [103] "voges–proskauer_reaction"                                        
    ## [104] "alpha-mannosidase"                                               
    ## [105] "d-fucose"                                                        
    ## [106] "beta-glucuronidase"                                              
    ## [107] "inositol"                                                        
    ## [108] "malonate"                                                        
    ## [109] "tween_20_or_40"                                                  
    ## [110] "ecosystem=environmental"                                         
    ## [111] "ecosystem=hostassociated"                                        
    ## [112] "ecosystemcategory=animal"                                        
    ## [113] "ecosystemcategory=aquatic"                                       
    ## [114] "ecosystemcategory=biotransformation"                             
    ## [115] "ecosystemcategory=fish"                                          
    ## [116] "ecosystemcategory=foodproduction"                                
    ## [117] "ecosystemcategory=human"                                         
    ## [118] "ecosystemcategory=insecta"                                       
    ## [119] "ecosystemcategory=mammals"                                       
    ## [120] "ecosystemcategory=plants"                                        
    ## [121] "ecosystemcategory=solidwaste"                                    
    ## [122] "ecosystemcategory=terrestrial"                                   
    ## [123] "ecosystemsubtype=blood"                                          
    ## [124] "ecosystemsubtype=cerebrospinalfluid"                             
    ## [125] "ecosystemsubtype=fecal"                                          
    ## [126] "ecosystemsubtype=foregut"                                        
    ## [127] "ecosystemsubtype=hydrothermalvents"                              
    ## [128] "ecosystemsubtype=largeintestine"                                 
    ## [129] "ecosystemsubtype=lentic"                                         
    ## [130] "ecosystemsubtype=lotic"                                          
    ## [131] "ecosystemsubtype=oceanic"                                        
    ## [132] "ecosystemsubtype=oral"                                           
    ## [133] "ecosystemsubtype=petrochemical"                                  
    ## [134] "ecosystemsubtype=saltcrystallizerponds"                          
    ## [135] "ecosystemsubtype=wetlands"                                       
    ## [136] "ecosystemtype=agriculturalfield"                                 
    ## [137] "ecosystemtype=composting"                                        
    ## [138] "ecosystemtype=digestivesystem"                                   
    ## [139] "ecosystemtype=industrialwastewater"                              
    ## [140] "ecosystemtype=marine"                                            
    ## [141] "ecosystemtype=phylloplane"                                       
    ## [142] "ecosystemtype=reproductivesystem"                                
    ## [143] "ecosystemtype=respiratorysystem"                                 
    ## [144] "ecosystemtype=rhizoplane"                                        
    ## [145] "ecosystemtype=soil"                                              
    ## [146] "ecosystemtype=thermalsprings"                                    
    ## [147] "knownhabitats=aquatic"                                           
    ## [148] "knownhabitats=biofilm"                                           
    ## [149] "knownhabitats=creosotecontaminatedsoil"                          
    ## [150] "knownhabitats=deepsea"                                           
    ## [151] "knownhabitats=feces"                                             
    ## [152] "knownhabitats=freshwater"                                        
    ## [153] "knownhabitats=gastrointestinaltract"                             
    ## [154] "knownhabitats=host"                                              
    ## [155] "knownhabitats=hotspring"                                         
    ## [156] "knownhabitats=humanoralcavity"                                   
    ## [157] "knownhabitats=insectendosymbiont"                                
    ## [158] "knownhabitats=intestinaltract"                                   
    ## [159] "knownhabitats=marine"                                            
    ## [160] "knownhabitats=rhizosphere"                                       
    ## [161] "knownhabitats=sediment"                                          
    ## [162] "knownhabitats=sludge"                                            
    ## [163] "knownhabitats=soil"                                              
    ## [164] "knownhabitats=wastewater"                                        
    ## [165] "phenotypes=acidophile"                                           
    ## [166] "phenotypes=alkaliphile"                                          
    ## [167] "specificecosystem=fecal"                                         
    ## [168] "specificecosystem=rumen"                                         
    ## [169] "specificecosystem=sediment"                                      
    ## [170] "specificecosystem=sputum"                                        
    ## [171] "ecosystemcategory=wastewater"                                    
    ## [172] "ecosystemsubtype=intertidalzone"                                 
    ## [173] "ecosystemtype=dairyproducts"                                     
    ## [174] "knownhabitats=food"                                              
    ## [175] "knownhabitats=humanairways"                                      
    ## [176] "knownhabitats=hydrothermalvent"                                  
    ## [177] "knownhabitats=plantroot"                                         
    ## [178] "knownhabitats=rootnodule"                                        
    ## [179] "ecosystemcategory=birds"                                         
    ## [180] "ecosystemsubtype=vagina"                                         
    ## [181] "ecosystemtype=circulatorysystem"                                 
    ## [182] "knownhabitats=mud"                                               
    ## [183] "ecosystemsubtype=nasopharyngeal"                                 
    ## [184] "knownhabitats=endosymbiont"                                      
    ## [185] "knownhabitats=oralcavity"                                        
    ## [186] "ecosystemsubtype=urethra"                                        
    ## [187] "ecosystemtype=freshwater"                                        
    ## [188] "ecosystemtype=skin"                                              
    ## [189] "knownhabitats=birdsintestinalmicroflora"                         
    ## [190] "knownhabitats=seawater"                                          
    ## [191] "specificecosystem=urine"                                         
    ## [192] "knownhabitats=humanintestinalmicroflora"                         
    ## [193] "knownhabitats=oilfields"                                         
    ## [194] "knownhabitats=plantsymbiont"                                     
    ## [195] "knownhabitats=skin"                                              
    ## [196] "ecosystemcategory=bioremediation"                                
    ## [197] "ecosystemsubtype=mine"                                           
    ## [198] "ecosystemsubtype=ponds"                                          
    ## [199] "ecosystemtype=geologic"                                          
    ## [200] "ecosystemtype=metal"                                             
    ## [201] "ecosystemtype=nonmarinesalineandalkaline"                        
    ## [202] "knownhabitats=animalgastrointestinaltract"                       
    ## [203] "knownhabitats=compost"                                           
    ## [204] "knownhabitats=gingivalcrevices"                                  
    ## [205] "knownhabitats=humanvaginalmicroflora"                            
    ## [206] "knownhabitats=pig"                                               
    ## [207] "knownhabitats=plants"                                            
    ## [208] "knownhabitats=bovinerumen"                                       
    ## [209] "knownhabitats=bovine"                                            
    ## [210] "knownhabitats=surfacewater"                                      
    ## [211] "knownhabitats=humanfecal"                                        
    ## [212] "knownhabitats=humanskin"                                         
    ## [213] "bioticrelationship=symbiotic"                                    
    ## [214] "cellarrangement=chains"                                          
    ## [215] "cellarrangement=clusters"                                        
    ## [216] "cellarrangement=filaments"                                       
    ## [217] "cellarrangement=pairs"                                           
    ## [218] "cellarrangement=singles"                                         
    ## [219] "energysource=autotroph"                                          
    ## [220] "energysource=chemoorganotroph"                                   
    ## [221] "energysource=heterotroph"                                        
    ## [222] "energysource=lithotroph"                                         
    ## [223] "energysource=methylotroph"                                       
    ## [224] "energysource=photoautotroph"                                     
    ## [225] "energysource=photosynthetic"                                     
    ## [226] "energysource=phototroph"                                         
    ## [227] "flagellarpresence"                                               
    ## [228] "gram_stain=positive"                                             
    ## [229] "growth_in_groups"                                                
    ## [230] "habitat=aquatic"                                                 
    ## [231] "habitat=freeliving"                                              
    ## [232] "habitat=hostassociated"                                          
    ## [233] "habitat=single"                                                  
    ## [234] "habitat=terrestrial"                                             
    ## [235] "halophilic"                                                      
    ## [236] "host=insectsgeneral"                                             
    ## [237] "host=insectstermites"                                            
    ## [238] "host=mammalscarnivora"                                           
    ## [239] "host=mammalsherbivores"                                          
    ## [240] "host=mammalsman"                                                 
    ## [241] "host=mammalspig"                                                 
    ## [242] "host=marineinvertebrates"                                        
    ## [243] "host=plantsexceptlegumes"                                        
    ## [244] "host=plantslegumes"                                              
    ## [245] "host=ticks"                                                      
    ## [246] "mammalian_pathogen=enteric"                                      
    ## [247] "mammalian_pathogen=nervous_system"                               
    ## [248] "mammalian_pathogen=oportunisticnosocomial"                       
    ## [249] "mammalian_pathogen=oral_cavity"                                  
    ## [250] "mammalian_pathogen=respiratory_lungdisease"                      
    ## [251] "mammalian_pathogen=respiratory"                                  
    ## [252] "mammalian_pathogen=respiratory_throatnoseeyes"                   
    ## [253] "mammalian_pathogen=urogenital"                                   
    ## [254] "mammalian_pathogen=urogenital_reproductive"                      
    ## [255] "mammalian_pathogen=urogenital_urinary"                           
    ## [256] "metabolism=biomassdegrader"                                      
    ## [257] "metabolism=cellulosedegrader"                                    
    ## [258] "metabolism=ethanolproduction"                                    
    ## [259] "metabolism=hydrogensulfidegasrelease"                            
    ## [260] "metabolism=ironoxidizer"                                         
    ## [261] "metabolism=ironreducer"                                          
    ## [262] "metabolism=methanogen"                                           
    ## [263] "metabolism=nitrifying"                                           
    ## [264] "metabolism=nitrogenfixation"                                     
    ## [265] "metabolism=nitrogenproducer"                                     
    ## [266] "metabolism=pahdegrading"                                         
    ## [267] "metabolism=sulfatereducer"                                       
    ## [268] "metabolism=sulfuroxidizer"                                       
    ## [269] "mobility"                                                        
    ## [270] "motility"                                                        
    ## [271] "oxygenreq=facultative"                                           
    ## [272] "oxygenreq=strictaero"                                            
    ## [273] "oxygenreq=strictanaero"                                          
    ## [274] "pathogenic_in_mammals"                                           
    ## [275] "pathogenic_in_plants"                                            
    ## [276] "radioresistance"                                                 
    ## [277] "shape=bacilli"                                                   
    ## [278] "shape=coccus"                                                    
    ## [279] "shape=filamentous"                                               
    ## [280] "shape=spirilla"                                                  
    ## [281] "shape=tailed"                                                    
    ## [282] "sporulation"                                                     
    ## [283] "temperaturerange=hyperthermophilic"                              
    ## [284] "temperaturerange=mesophilic"                                     
    ## [285] "temperaturerange=thermophilic"                                   
    ## [286] "habitat=multiple"                                                
    ## [287] "oxygenreq=microaerophilic"                                       
    ## [288] "temperaturerange=psychrophilic"                                  
    ## [289] "cellarrangement=tetrads"                                         
    ## [290] "habitat=specialized"                                             
    ## [291] "energysource=chemoautotroph"                                     
    ## [292] "energysource=chemolithotroph"                                    
    ## [293] "mammalian_pathogen=bone"                                         
    ## [294] "energysource=chemoheterotroph"                                   
    ## [295] "energysource=chemolithoautotroph"                                
    ## [296] "host=fish"                                                       
    ## [297] "mammalian_pathogen=cardiovascular"                               
    ## [298] "metabolism=sulfurrespiration"                                    
    ## [299] "habitat=aquatic_salinewater"                                     
    ## [300] "metabolism=ammoniaoxidizer"                                      
    ## [301] "metabolism=storespolyhydroxybutyrate"                            
    ## [302] "pathogenic_in_fish"                                              
    ## [303] "energysource=oligotroph"                                         
    ## [304] "metabolism=acetogen"                                             
    ## [305] "mammalian_pathogen=cardiovascular_blood"                         
    ## [306] "mammalian_pathogen=skin_softtissues"                             
    ## [307] "mammalian_pathogen=softtissues"                                  
    ## [308] "(secondari,metabolit,mycelium,antibiot,spore)"                   
    ## [309] "(rumen,bovin,rumin,cattl,degrad)"                                
    ## [310] "(australia,infecti,queensland,fill,fluid)"                       
    ## [311] "(vaccin,immun,antibodi,infect,protect)"                          
    ## [312] "(ethanol,ferment,acet,succin,lactat)"                            
    ## [313] "(aerial,mycelium,spore,hypha,soil)"                              
    ## [314] "(symbiosi,replicon,nitrogen,nitrogenfix,streptomycinresist)"     
    ## [315] "(prophag,instanc,variat,diverg,newli)"                           
    ## [316] "(bacteriochlorophyl,photosystem,photosynthesi,chlorophyl,oxygen)"
    ## [317] "(spring,mat,hot,yellowston,moder)"                               
    ## [318] "(sauc,lactic,soi,salt,ferment)"                                  
    ## [319] "(vertic,alkaliphil,bacteriom,sharpshoot,agreement)"              
    ## [320] "(sporeform,gramposit,nonmotil,motil,rodshap)"                    
    ## [321] "(benzen,toluen,degrad,aromat,hydrocarbon)"                       
    ## [322] "(blight,fire,shoot,pathogen,japan)"                              
    ## [323] "(pyren,pah,naphthalen,polycycl,anthracen)"                       
    ## [324] "(brucellosi,infect,transmit,vaccin,pathogen)"                    
    ## [325] "(buruli,chancroid,ulcer,mycolacton,endem)"                       
    ## [326] "(ocean,coastal,plankton,inorgan,suspend)"                        
    ## [327] "(unicellular,photosystem,photosynthesi,ocean,fixat)"             
    ## [328] "(subsurfac,sulfatereduc,piezophil,aquif,groundwat)"              
    ## [329] "(sludg,wastewat,reactor,bioreactor,kei)"                         
    ## [330] "(fe,anod,mfc,electrod,electr)"                                   
    ## [331] "(staphylococci,staphylococc,methicillin,urinari,coagulaseneg)"   
    ## [332] "(nitrogenfix,symbiosi,fixat,rhizospher,rhizobia)"                
    ## [333] "(tickborn,pathogen,virul,rickettsiosi,infect)"                   
    ## [334] "(cystic,fibrosi,patient,lung,infect)"                            
    ## [335] "(radiat,ioniz,usa,desicc,repair)"                                
    ## [336] "(gastric,gastriti,spiralshap,biopsi,microaerophil)"              
    ## [337] "(methylotroph,methanol,formaldehyd,pinkpig,methylamin)"          
    ## [338] "(rot,crop,econom,phytopathogen,unclear)"                         
    ## [339] "(alkaliphil,sodiumdepend,halotoler,proton,transloc)"             
    ## [340] "(phosphoru,ebpr,wastewat,polyphosph,treatment)"                  
    ## [341] "(flora,vagin,tract,vaginosi,reproduct)"                          
    ## [342] "(virul,island,capsul,invas,transport)"                           
    ## [343] "(borreliosi,infect,pathogen,tickborn,antigen)"                   
    ## [344] "(pha,polyhydroxyalkano,phb,accumul,carbon)"                      
    ## [345] "(salin,optimum,hypersalin,salt,oil)"                             
    ## [346] "(deepsea,piezophil,pressur,depth,hydrostat)"                     
    ## [347] "(toxin,crystal,insecticid,gut,spore)"                            
    ## [348] "(glide,motil,motor,pigment,pathogen)"                            
    ## [349] "(nitrogenfix,symbiosi,fixat,toluen,protect)"                     
    ## [350] "(permafrost,siberian,psychrophil,cold,antarct)"                  
    ## [351] "(haloarchaea,hypersalin,archaeal,seafood,nacl)"                  
    ## [352] "(paddi,anox,bog,toluen,divers)"                                  
    ## [353] "(tetanu,toxin,spore,botul,toxoid)"                               
    ## [354] "(ehrlichiosi,monocyt,granulocyt,macrophag,anaplasmosi)"          
    ## [355] "(prei,predatori,predat,attack,flagellum)"                        
    ## [356] "(tooth,dental,cari,caviti,plaqu)"                                
    ## [357] "(uranium,bioremedi,subsurfac,remedi,contamin)"                   
    ## [358] "(blackleg,rot,stem,unclear,pathogen)"                            
    ## [359] "(bioaugment,wastewat,wast,degrad,biodegrad)"                     
    ## [360] "(nitrit,ammoniaoxid,nitrif,ammonium,nitrat)"                     
    ## [361] "(cytochrom,fe,heme,ctype,dissimilatori)"                         
    ## [362] "(gut,diet,glycan,obes,reduc)"                                    
    ## [363] "(fe,acceptor,dissimilatori,metal,donor)"                         
    ## [364] "(magnetosom,magnetit,amb1,magnetotaxi,crystal)"                  
    ## [365] "(hyperthermophil,archaeal,hydrotherm,vent,heterotroph)"          
    ## [366] "(dehalogen,ethen,dehalogenas,dechlorin,halogen)"                 
    ## [367] "(kimchi,ferment,korean,ingredi,season)"                          
    ## [368] "(sheath,south,coast,korea,hole)"                                 
    ## [369] "(vent,hydrotherm,deepsea,chemolithoautotroph,sulfuroxid)"        
    ## [370] "(syntroph,acetateoxid,acet,isobutyr,fatti)"                      
    ## [371] "(lous,nymph,relaps,patient,adult)"                               
    ## [372] "(infect,patient,pathogen,virul,opportunist)"                     
    ## [373] "(thermophil,spring,hot,cellulolyt,optimum)"                      
    ## [374] "(spore,crystal,sporul,toxic,polysaccharid)"                      
    ## [375] "(legum,symbiosi,rhizobia,nod,stem)"                              
    ## [376] "(alkan,oil,crude,hydrocarbon,degrad)"                            
    ## [377] "(sulfatereduc,sulfat,dissimilatori,sulfit,acceptor)"             
    ## [378] "(methan,methanogenesi,acet,methanol,dioxid)"                     
    ## [379] "(lactic,chees,food,ferment,milk)"                                
    ## [380] "(meat,raw,ferment,fresh,food)"                                   
    ## [381] "(heterocyst,fixat,veget,aquat,carbon)"                           
    ## [382] "(japan,paddi,anox,gramneg,rod)"                                  
    ## [383] "(denitrif,nitrat,nitrit,reductas,nitrou)"                        
    ## [384] "(cellulos,cellulosom,cellulolyt,xylan,cellulas)"                 
    ## [385] "(hypha,gramposit,aerial,antibiot,spore)"                         
    ## [386] "(nonpathogen,blight,fire,shoot,motil)"                           
    ## [387] "(virul,pathogen,highli,econom,motil)"                            
    ## [388] "(spring,hot,arsen,optim,arsenit)"                                
    ## [389] "(periodont,gingiv,bone,dental,plaqu)"                            
    ## [390] "(relaps,tickborn,lous,transmit,epidem)"                          
    ## [391] "(anox,sediment,ground,nonmotil,reclassifi)"                      
    ## [392] "(acidophil,thermophil,thermoacidophil,heterotroph,dissimilatori)"
    ## [393] "(nocardiosi,subord,pulmonari,immunocompromis,chronic)"           
    ## [394] "(acidophil,thermophil,pyrit,bioleach,drainag)"                   
    ## [395] "(leprosi,india,brazil,nerv,patient)"                             
    ## [396] "(fungal,antifung,phenazin,biocontrol,rot)"                       
    ## [397] "(beer,spoilag,spoil,lactic,beverag)"                             
    ## [398] "(faec,nonsporeform,nonmotil,gramneg,rodshap)"                    
    ## [399] "(psychrophil,cold,sediment,inhabit,irregular)"                   
    ## [400] "(goat,mastiti,mycoplasm,polyarthr,cow)"                          
    ## [401] "(soybean,legum,max,rhizobia,fastgrow)"                           
    ## [402] "(autotroph,replic,fixat,metabol,aggreg)"                         
    ## [403] "(smallest,intein,extrachromosom,freeliv,ocean)"                  
    ## [404] "(symbiosi,island,nativ,australia,dispens)"                       
    ## [405] "(subord,stalk,mother,swarmer,averag)"                            
    ## [406] "(hydrogenotroph,nacl,optimum,sakai,moder)"                       
    ## [407] "(appendag,nearest,distinct,rich,resembl)"                        
    ## [408] "(ferment,spoilag,lactic,kimchi,korean)"                          
    ## [409] "(cem,mare,metriti,contagi,stallion)"                             
    ## [410] "(sulphur,acidophil,metal,reduc,fe)"                              
    ## [411] "(xylanas,xylan,cellulas,hydrolysi,flagellin)"                    
    ## [412] "(faec,sporeform,gramposit,rodshap,capabl)"                       
    ## [413] "(gramposit,motil,sporeform,whippl,multisystem)"                  
    ## [414] "(rhizospher,nitrogenfix,nitrogen,replicon,gramneg)"              
    ## [415] "(ectoin,salin,salt,mutant,optimum)"                              
    ## [416] "(halotoler,salt,mesophil,pictur,iran)"                           
    ## [417] "(disproportion,mesophil,thiosulf,metabol,sulfatereduc)"          
    ## [418] "(psychrotoler,nearest,flat,glucos,chlorid)"                      
    ## [419] "knownhabitats=urogenitaltract"                                   
    ## [420] "ecosystemsubtype=alkaline"                                       
    ## [421] "mammalian_pathogen=cardiovascular_heart_bloodvessels"            
    ## [422] "metabolism=carbondioxidefixation"                                
    ## [423] "(bioluminesc,gramneg,nonmotil,reliabl,biodegrad)"                
    ## [424] "(subsurfac,geochem,deep,aquif,depth)"

#### read in data from Barberan et al. 2016 (IJSEM: <https://figshare.com/articles/International_Journal_of_Systematic_and_Evolutionary_Microbiology_IJSEM_phenotypic_database/4272392>)

``` r
path = "4272392/"
#read table

ijsem<-read.delim(paste0(path,"IJSEM_pheno_db_v1.0.txt"), sep="\t", header=T, check.names=F, fill=T,
                  na.strings=c("NA", "", "Not indicated", " Not indicated","not indicated", "Not Indicated", "n/a", "N/A", "Na", "Not given", "not given","Not given for yeasts", "not indicated, available in the online version", "Not indicated for yeasts", "Not Stated", "Not described for yeasts", "Not determined", "Not determined for yeasts"))

#simplify column names
colnames(ijsem)<-c("Habitat", "Year", "DOI", "rRNA16S", "GC", "Oxygen",
                  "Length", "Width", "Motility", "Spore", "MetabAssays", "Genus", "Species", "Strain", "pH_optimum", "pH_range", "Temp_optimum", "Temp_range", "Salt_optimum", "Salt_range", "Pigment", "Shape", "Aggregation", "FirstPage", "CultureCollection", "CarbonSubstrate", "Genome", "Gram", "Subhabitat", "Biolog")

#clean Habitat column
levels(ijsem$Habitat)[levels(ijsem$Habitat)=="freshwater (river, lake, pond)"]<-"freshwater"
levels(ijsem$Habitat)[levels(ijsem$Habitat)=="freshwater sediment (river, lake, pond"]<-"freshwater sediment"

#clean Oxygen column
levels(ijsem$Oxygen)[levels(ijsem$Oxygen)=="aerobic"]<-"obligate aerobe"
levels(ijsem$Oxygen)[levels(ijsem$Oxygen)=="anerobic"]<-"obligate anerobe"
levels(ijsem$Oxygen)[levels(ijsem$Oxygen)=="microerophile"]<-"microaerophile"

#clean pH_optimum column
ijsem$pH_optimum<-as.character(ijsem$pH_optimum)
#this step splits the range values and takes the mean value
#values that are not numeric are transformed to NAs
ijsem$pH_optimum<-suppressWarnings(sapply(ijsem$pH_optimum, simplify=T, function(x){mean(as.numeric(unlist(strsplit(x, split="-", fixed=T))))}))
#remove pH values <0 and >10
ijsem$pH_optimum[ijsem$pH_optimum<0 | ijsem$pH_optimum>10]<-NA

#clean Temp_optimum column
ijsem$Temp_optimum<-as.character(ijsem$Temp_optimum)
#this step splits the range values and takes the mean value
#values that are not numeric are transformed to NAs
ijsem$Temp_optimum<-suppressWarnings(sapply(ijsem$Temp_optimum, simplify=T, function(x){mean(as.numeric(unlist(strsplit(x, split="-", fixed=T))))}))

#clean Salt_optimum column
ijsem$Salt_optimum<-as.character(ijsem$Salt_optimum)
#this step splits the range values and takes the mean value
#values that are not numeric are transformed to NAs
ijsem$Salt_optimum<-suppressWarnings(sapply(ijsem$Salt_optimum, simplify=T, function(x){mean(as.numeric(unlist(strsplit(x, split="-", fixed=T))))}))
#there are some formatting issues that should be solved

summary(ijsem)
```

    ##              Habitat          Year                          DOI      
    ##  other           :1853   Min.   :2004   10.1099/ijs.0.054098-0:  27  
    ##  soil            :1089   1st Qu.:2007   10.1099/ijs.0.051540-0:  26  
    ##  seawater        : 401   Median :2009   10.1099/ijs.0.051045-0:  25  
    ##  marine sediment : 329   Mean   :2009   10.1099/ijs.0.053306-0:  20  
    ##  plant associated: 297   3rd Qu.:2012   10.1099/ijs.0.63527-0 :  12  
    ##  (Other)         :1139   Max.   :2015   (Other)               :5010  
    ##  NA's            :  20                  NA's                  :   8  
    ##       rRNA16S           GC                        Oxygen    
    ##  JN565849 :  28   72     :  48   obligate aerobe     :3206  
    ##  HG1315102:  25   67     :  42   anaerobic           : 573  
    ##  JX402080 :  24   40.8   :  41   facultative aerobe  :  86  
    ##  KC525204 :  23   68.5   :  40   facultative anaerobe: 617  
    ##  KC447383 :   9   71     :  35   microaerophile      :  45  
    ##  (Other)  :4940   (Other):4279   NA's                : 601  
    ##  NA's     :  79   NA's   : 643                              
    ##      Length         Width                                   Motility   
    ##  2      : 165   0.5    : 348   axial filament                   :   9  
    ##  2.5    : 155   0.6    : 199   flagella                         :1157  
    ##  1.5    : 136   0.7    : 173   gliding                          : 166  
    ##  3      : 109   0.75   : 173   motile, but unspecified structure: 707  
    ##  1.75   :  94   0.4    : 172   non-motile                       :2384  
    ##  (Other):3150   (Other):2852   NA's                             : 705  
    ##  NA's   :1319   NA's   :1211                                           
    ##   Spore     
    ##  no  :2423  
    ##  yes :1028  
    ##  NA's:1677  
    ##             
    ##             
    ##             
    ##             
    ##                                                             MetabAssays  
    ##  catalase positive, oxidase positive                              : 369  
    ##  catalase positive                                                : 244  
    ##  catalase positive, nitrate reduction to nitrite, oxidase positive: 173  
    ##  aesculin hydrolysis                                              : 118  
    ##  aesculin hydrolysis, catalase positive, oxidase positive         : 106  
    ##  (Other)                                                          :3345  
    ##  NA's                                                             : 773  
    ##             Genus               Species         Strain    
    ##  Bacillus      : 119   soli         :  57   7747T  :  26  
    ##  Streptomyces  : 106   marina       :  38   49061T :  25  
    ##  Paenibacillus :  78   xinjiangensis:  35   YDT    :  25  
    ##  Flavobacterium:  74   ginsengisoli :  32   J4T    :  18  
    ##  Lactobacillus :  72   marinus      :  31   J4     :   6  
    ##  Mycobacterium :  68   koreensis    :  30   (Other):5020  
    ##  (Other)       :4611   (Other)      :4905   NA's   :   8  
    ##    pH_optimum        pH_range     Temp_optimum     Temp_range  
    ##  Min.   : 0.750   06-Sep : 216   Min.   :  3.0   Oct-37 : 210  
    ##  1st Qu.: 7.000   06-Aug : 189   1st Qu.: 27.5   15-37  : 191  
    ##  Median : 7.000   7      : 167   Median : 30.0   Oct-40 : 158  
    ##  Mean   : 7.208   05-Sep : 152   Mean   : 31.4   Apr-37 : 154  
    ##  3rd Qu.: 7.500   05-Oct : 143   3rd Qu.: 34.0   20-37  : 143  
    ##  Max.   :10.000   (Other):2974   Max.   :300.0   (Other):3754  
    ##  NA's   :1634     NA's   :1287   NA's   :764     NA's   : 518  
    ##   Salt_optimum       Salt_range   Pigment                     Shape     
    ##  Min.   :  0.000   0      : 230   no  : 721   cocci              : 464  
    ##  1st Qu.:  0.500   0-2    : 183   yes :3118   ovoid/coccobacillus: 376  
    ##  Median :  2.000   0-1    : 182   NA's:1289   rod                :3773  
    ##  Mean   :  3.238   0-3    : 172               spirillum/corkscrew:  48  
    ##  3rd Qu.:  3.500   0-5    : 150               NA's               : 467  
    ##  Max.   :232.000   (Other):2937                                         
    ##  NA's   :2387      NA's   :1274                                         
    ##  Aggregation    FirstPage                   CultureCollection
    ##  chain:1135   60     :  40   CECT8312T|DSM27088T     :  17   
    ##  clump: 670   33     :  34   DSM25287T|NCCB100398T   :  15   
    ##  none : 204   39     :  33   JCM18565T|KCTC29126T    :  15   
    ##  NA's :3119   27     :  28   CGMCC1.12331T|JCM18732T :  12   
    ##               1471   :  13   ATCCBAA-1391T|VKMB-2447T:   3   
    ##               (Other):4979   (Other)                 :5049   
    ##               NA's   :   1   NA's                    :  17   
    ##                                                                                                                                                                                                                    CarbonSubstrate
    ##  Tween 80                                                                                                                                                                                                                  :  29  
    ##  glucose                                                                                                                                                                                                                   :  26  
    ##  fructose, galactose, lactose, maltose, mannose, raffinose, sucrose                                                                                                                                                        :  19  
    ##  acetate, butanol, ethanol, fructose, galactose, glucosamine, glucose, glycerol, lactate, maltose, melibiose, propionic acid (propionate), pyruvic acid (pyruvate), raffinose, succinic acid (succinate), sucrose, valerate:  18  
    ##  acetate                                                                                                                                                                                                                   :  16  
    ##  (Other)                                                                                                                                                                                                                   :4570  
    ##  NA's                                                                                                                                                                                                                      : 450  
    ##   Genome                                            Gram     
    ##  CAUK01000001\xe4\xf3\xf1 CAUK01000006:  15   negative:2871  
    ##  CAUK01000001\xe4\xf3\xf1CAUK01000006 :   3   positive:1846  
    ##  CAUK01000001-CAUK01000006            :   2   variable:  85  
    ##   AB208062                            :   1   NA's    : 326  
    ##   CAUJ01000001\xe4\xf3\xf1CAUJ01000008:   1                  
    ##  (Other)                              :  67                  
    ##  NA's                                 :5039                  
    ##                Subhabitat       Biolog    
    ##  air sample         :  24   No     :3811  
    ##  tidal flat sediment:  22   Yes    :1316  
    ##  Sludge             :  18   Yes, No:   1  
    ##  salt lake          :  17                 
    ##  marine sponge      :  16                 
    ##  (Other)            :1868                 
    ##  NA's               :3163
