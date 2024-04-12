
# Upper Necaxa Totonac morphological analyser
INTRODUCTION TO THE MORPHOLOGICAL ANALYSER OF Upper Necaxa Totonac.

# Definitions for Multichar_Symbols

## Analysis symbols

The morphological analyses of wordforms in Plains Cree are presented
in this system in terms of the following symbols.
(It is highly suggested to follow existing standards when adding new tags).

POS

* +Guess      
* +N	        
* +V	        
* +A	        

* +Adv        
* +CC	        
* +CS	        
* +Interj     
* +Pron       
* +Num        

* +Loc        

Verbal MSP
* +Prs  
* +Fut  
* +Prt  
* +Prf  

* +Ind  
* +Imp   Imperative
* +Opt   Optative,
* +Irr   Irrealis,

* +Int   Interdiction,
* +Dur   Durative

* +Impf   Imperfective
* +Pfv    Perfective
* +Prog    Progressive

* +1Sg     first singular
* +2Sg     etc
* +3Sg    
* +3oSg    3o is obviative,
* +3iSg    3i is indefinite

* +1Pl     1Pl is exclusive plural (I, them, not you)
* +2Pl    
* +3Pl    
* +3oPl   
* +3iPl   
* +12Pl    12Pl is inclusive plural (I, you, ...)

* +1SgO    objective conjugation
* +2SgO   
* +3SgO   
* +SgO    
* +3oSgO   obviative with objective conjugation
* +3iSgO  
* +1PlO   
* +P2lO   
* +3PlO   
* +PlO    
* +3oPlO  
* +3iPlO  

* +Inf     infinitive (infinite?)
* +Pos     postitive
* +Neg     negative
* +ConNeg  accompanying negative form

Nominal MSP
* +Sg		  singular
* +Pl		  plural

* +Px1Sg	  person prefixes for nouns
* +Px2Sg	 
* +Px3Sg	 
* +Px1Pl	  obviative
* +Px12Pl	  inclusive
* +Px2Pl	 
* +Px3Pl	 

* %> 		  suffix border
2Sg Stress shift ^SS

* +Err/Orth  tag for substandard forms

* +Symbol = independent symbols in the text stream, like £, €, ©

## Flag diacritics

These are documented in Chapter 8 of Beesley/Karttunen, p. 456 zB.

### Intransitives

* @U.verb.1sgindep@ 	
* @U.verb.2sgindep@ 	
* @U.verb.3sgindep@ 	
* @U.verb.3osgindep@   delete?
* @U.verb.3isgindep@    delete?
* @U.verb.1plindep@ 	
* @U.verb.12plindep@ 	
* @U.verb.2plindep@ 	
* @U.verb.3plindep@ 	

* @U.verb.1sgsbj@ 	
* @U.verb.2sgsbj@ 	
* @U.verb.3sgsbj@ 	
* @U.verb.3osgsbj@  	 delete ?
* @U.verb.3isgsbj@      delete?
* @U.verb.1plsbj@ 	
* @U.verb.12plsbj@ 	
* @U.verb.2plsbj@ 	
* @U.verb.3plsbj@ 	

* @U.verb.2sgimp@		
* @U.verb.1plimp@		
* @U.verb.2plimp@		

### Transitives

* @U.verb.1sgosgindep@  	
* @U.verb.1sgoplindep@  	

* @U.verb.2sg1sgindep@  	
* @U.verb.2sg3sgindep@  	
* @U.verb.2sgoplindep@  	

* @U.verb.3sgosgindep@  	
* @U.verb.3sgoplindep@  	

* @U.verb.1ploindep@ 	  	
* @U.verb.12ploindep@   	
* @U.verb.2ploindep@ 	  	
* @U.verb.3ploindep@ 	  	

* @U.tense.prs@		  	
* @U.tense.prt@		  	

### Nouns

* @U.noun.1sg@		  	
* @U.noun.2sg@		  	
* @U.noun.3sg@		  	
* @U.noun.3isg@		  	
* @U.noun.3osg@		  	
* @U.noun.1pl@		  	
* @U.noun.12pl@		  	
* @U.noun.2pl@		  	
* @U.noun.3pl@		  	

* @U.noun.abs@ 		  	

We have manually optimised the structure of our lexicon using following
flag diacritics to restrict morhpological combinatorics - only allow compounds
with verbs if the verb is further derived into a noun again:
|  @P.NeedNoun.ON@ | (Dis)allow compounds with verbs unless nominalised
|  @D.NeedNoun.ON@ | (Dis)allow compounds with verbs unless nominalised
|  @C.NeedNoun@ | (Dis)allow compounds with verbs unless nominalised

For languages that allow compounding, the following flag diacritics are needed
to control position-based compounding restrictions for nominals. Their use is
handled automatically if combined with +CmpN/xxx tags. If not used, they will
do no harm.
|  @P.CmpFrst.FALSE@ | Require that words tagged as such only appear first
|  @D.CmpPref.TRUE@ | Block such words from entering ENDLEX
|  @P.CmpPref.FALSE@ | Block these words from making further compounds
|  @D.CmpLast.TRUE@ | Block such words from entering R
|  @D.CmpNone.TRUE@ | Combines with the next tag to prohibit compounding
|  @U.CmpNone.FALSE@ | Combines with the prev tag to prohibit compounding
|  @P.CmpOnly.TRUE@ | Sets a flag to indicate that the word has passed R
|  @D.CmpOnly.FALSE@ | Disallow words coming directly from root.

Use the following flag diacritics to control downcasing of derived proper
nouns (e.g. Finnish Pariisi -> pariisilainen). See e.g. North Sámi for how to use
these flags. There exists a ready-made regex that will do the actual down-casing
given the proper use of these flags.
|  @U.Cap.Obl@ | Allowing downcasing of derived names: deatnulasj.
|  @U.Cap.Opt@ | Allowing downcasing of derived names: deatnulasj.

 LEXICON Root 		  is where it all starts

* Verbs ;	             

* * *

<small>This (part of) documentation was generated from [src/fst/morphology/root.lexc](https://github.com/giellalt/lang-tku/blob/main/src/fst/morphology/root.lexc)</small>
