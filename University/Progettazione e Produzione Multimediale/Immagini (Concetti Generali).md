---
sticker: emoji//0031-fe0f-20e3
Order: "1"
---
## Immagini Digitali
Le immagini digitali sono ottenute scattando una scena o scansionando un documento.
L'immagine digitale è rappresentata da una griglia di punti (pixel), ad ognuno dei quali è assegnato un valore (rappresentato in codice binario).
I bit per ogni pixel sono salvati come una sequenza nel computer, solitamente ridotta grazie ad espressioni matematiche (compressione).
### Bit Depth
Per *Bit Depth* si intende il numero di bit usati per definire ogni pixel. Un'immagine **Bitonale**, per esempio, è rappresentata da pixel composti da 1 bit ciascuno (che rappresentano il colore nero o bianco); un immagine in **Scala di Grigi** usa più bit per pixel, fornendo così ulteriori informazioni (tra 2 e 8), infine un immagine a **Colori** viene rappresentata con un bit depth tra 8 e 24.
### Color Image Formation
La *Color Image Formation* è determinata dalla distribuzione di potenza radiante relativa alla luce incidente, il riflesso dei materiali e le caratteristiche della fotocamera osservatrice.
![[Pasted image 20250517163433.png]]
$$C(\lambda)=m_{b}(\vec{n},\vec{s})\int_{\lambda}E(\lambda)\rho_{b}(\lambda)f_{C}(\lambda)\ d\lambda+m_{s}(\vec{n},\vec{s},\vec{v})\int_{\lambda}E(\lambda)\rho_{s}(\lambda)f_{C}(\lambda)\ d\lambda$$

| $\rho_{s}(\lambda)$ | Surface Albedo             | Scene and Viewpoint Invariant |
| ------------------- | -------------------------- | ----------------------------- |
| $\rho_{b}(\lambda)$ | Body Reflectance           | Object Material Dependent     |
| $E(\lambda)$        | Radiant Power Distribution | Scene Dependent               |
| $\vec{n}$           | Object Surface Normal      | Object Shape Variant          |
| $\vec{s}$           | Illumination Direction     | Viewpoint Variant             |
| $\vec{v}$           | Viewer's Direction         | Viewpoint Variant             |
| $f_{C}(\lambda)$    | Sensor Sensitivity         | Device Dependent              |
### Digital RGB Cameras
Le immagini digitali sono ottenute da fotocamere digitali che usano sensori CMOS o CCD per acquisire le lunghezza d'onda dei tre segnali dei colori: *R* (Red), *G* (Green), *B* (Blue). Il motivo per cui i canali utilizzati nei sensori, ovvero rosso, verde e blue, deriva dal modo in cui l'occhio umano opera.
Lo spettro della luce riflessa può essere rappresentato da un vettore di tre elemento, i cui valori sono le proporzioni di ognuno dei colori primari RGB presenti.
Si utilizzano i valori di *Tristimulus*:
$$
RGB \ Camera \ Value= Color\ *\ Tristi\mu lus
$$
$$\begin{align}
&R=\int_{\lambda}E(\lambda)\rho_{Skin}(\lambda)f_{R}(\lambda)\ d\lambda \\
&G=\int_{\lambda}E(\lambda)\rho_{Skin}(\lambda)f_{G}(\lambda)\ d\lambda \\
&B=\int_{\lambda}E(\lambda)\rho_{Skin}(\lambda)f_{B}(\lambda)\ d\lambda
\end{align}$$
Le fotocamere digitali RGB usano un *Bayer Filter*, con un rapporto RGB 1:2:1. Questo per ottenere maggiore luminosità rispetto alla risoluzione cromatico (in quanto il verde è più importante per l'occhio umano)
![[Pasted image 20250517171001.png]]
I sensori CCD hanno una griglia di sensori rossi, verdi e blu ordinati in modo che la prima riga sia GBG e la successiva RGR (sequenze che sono poi ripetute nelle righe successive).
<sup>Un alternativa al un Bayer Filter e l'uso di tre detecotr spearari</sup>
### Algoritmi di Demosaicing
Siccome originariamente ad ogni pixel corrisponde solo un colore tra i tre primari, non è possibile determinare accuratamente la luce riflessa catturata. È necessario quindi un algoritmo per stimare tutti i colori di tutti i pixel.
Per ottenere un immagine a colori si usa quindi un algoritmo di *Demosaicing*, il quale utilizza l'interpolazione per ottenere tutti i valori mancanti per ogni colore in tutta la griglia.
![[Pasted image 20250517171441.png]]
### Risoluzione e Dimensioni dei Pixel delle Immagini
Per *Risoluzione* si intende la densità di pixel per una certa area dell'immagine. Maggiore è la risoluzione e maggiore è la definizione dei dettagli. L'unità di misura usata è **PPI** (Pixel Per Inch).
Le *Dimensioni dei Pixel* indicano le misure orizzontali e verticali di una certa area dell'immagine in pixel. Può essere determinata moltiplicando sia la larghezza sia la larghezza (in pollici) per il PPI.
### Risoluzioni Fotocamere Digitali
In una fotocamera digitale la *Risoluzione* (*Pixel Density*) è il numero di pixel diviso l'area del sensore. Le *Pixel Dimensions* di una fotocamera digitale rappresentano in numero di pixel (in orizzontale e in verticale) che definiscono la risoluzione dell'immagine.

| **Camera Pixel Dimension** | **Camera Resolution (Pixel Density)** |
| -------------------------- | ------------------------------------- |
| $640\times 480$            | Low End                               |
| $1216\times 912$           | $1$ Megapixel                         |
| $1600\times 1200$          | 2 Megapixel                           |
| $2240\times 1680$          | $4$ Megapixel                         |
| $4064 \times 2704$         | $11$ Megapixel                        |
### Sensori Fotocamere e Pixel Size
Le fotocamere hanno una varia scelta per quanto riguarda la larghezza del sensore, a seconda della risoluzione usata. Solitamente le fotocamere comunino hanno sensori e pixel size ridotti in modo da ottenere più sensori da un solo wafer.
### Dimensioni Sensori Fotocamere
- Uno standard di grandezza del sensore per fotocamere comuni è tra i $4$ e $16$ mm (misurati diagonalmente).
- Le fotocamere industriali invece hanno un sensore 10-15 volte più grande

![[Pasted image 20250519122438.png]]
### Pixel Size Fotocamere
- Uno standard di pixel size per le fotocamere comuni varia tra $1.1$ microns, fino ai sensori full-frame di $8.4$ microns.
- Le fotocamere industriale con risoluzione fino a $2$ MP hanno dei pixel tra 9 $4.6$ e $7\ \mu m$.

![[Pasted image 20250519122733.png]]
### Risoluzione Fotocamere e Pixel Size
Il numero di Megapixel non indica accuratamente la qualità di una fotocamera, ci sono altri fattori da considerare, come:
- Quantità di luce
- Quantità di rumore tollerato
- Precisione nelle misure necessarie
Solitamente quando si utilizzano pixel più piccoli (a parità di dimensioni del sensore), si ha una maggiore quantità di dettagli, ma:
- Più piccoli sono i pixel, maggiore diventa la quantità necessaria di luce per catturare l'immagine
- Quando si ha poca luce, i pixel più piccoli introducono più rumore rispetto a quelli di dimensioni più grandi
- Se non si usa un obbiettivo di qualità non serve a niente avere un elevato numero di megapixel,
### Fotocamere ad Infrarossi e Termiche
- Le ad IR usano una luce ad infrarossi con lunghezza d'onda corta per illuminare l'area d'interesse. Una quantità di questa energia IR è riflessa poi verso la fotocamera, la quale provvede a generare l'immagine. Questa energia radia dagli oggetti in base alla loro variazione di temperatura.
- I sistemi di immagini a temperatura (?) usano invece energia IR con lunghezze d'onda lunghe o medie. Queste immagini sono passive e rilevano solo cambiamenti in temperatura. Il teromogramma (immagine rilevata) è una rappresentazione dei valori delle radiazioni infrarosse medie  che l'oggetto emette.
### Fotocamere Event Neuromorphic
Una telecamera a eventi utilizza un sensore ispirato alla biologia (come il falco per esempio): misura solo il "movimento" della scena osservata. Invece che catturare un flusso sincrono di frame, la telecamera a eventi misura i cambiamenti di luminosità (eventi) per ogni pixel

![[Pasted image 20250519124759.png]]
![[Pasted image 20250519124828.png]]
Le telecamere ad eventi non generano frame, ma eventi asincroni, che sono i cambiamenti d'intensità dei singoli pixel ad una risoluzione nell'ordine dei microsecondi (fino a $100,000$ fps).
Le fotocamere ad eventi hanno un elevato potenziale nei campi della robotica e computer vision, nello specifico in scenari complessi, come per esempio quando si ha un'alta velocità e un ampio range dinamico.
I vantaggi di queste telecamere sono quindi:
- Alta risoluzione temporale (ordine dei microsecondi)
- Range dinamico elevato ($140$ db vs $60$ db)
- Basso consumo ($1$ mW invece di $1$ W)
- Bassa latenza (ordine dei microsecondi)
- No motion blur
### Risoluzione Display
La risoluzione di un display digitale è il numero di pixel in ogni direzione dello schermo. La grandezza secondo la quale appare un'immagine dipende da due fattori:
- Il numero di pixel dell'immagine
- La risoluzione del display
Con *Risoluzione Nativa del Display* si intende la risoluzione dichiarata dal produttore dello schermo. Questa può comunque essere cambiata ad un valore più basso. Quando è in uso la risoluzione nativa si ha che ogni pixel dell'immagine corrisponde esattamente ad un pixel dello schermo.

| Resolution                                  |                          |          |
| ------------------------------------------- | ------------------------ | -------- |
| **HD**                                      | $1280\times 720$ pixel   | $720$ p  |
| **Full HD**                                 | $1920 \times 1080$ pixel | $1080$ p |
| **2K**                                      | $2048 \times 1080$ pixel |          |
| **QHD, WQHD ($2.5$K Quad High Definition)** | $2560\times 1440$ pixel  | $1440$ p |
| **UHD (Ultra High Definition)**             | $3840\times 2160$        | $2160$ p |
| **4K**                                      | $4096\times 2160$        | $2160$ p |
| **8K**                                      | $7680 \times 4320$       | $4320$ p |
### Recommendations for Web Images 
Per determinare accuratamente la corretta dimensione per un immagine da usare sul web, conta solo la dimensione dei pixel, quindi quanto è alta e larga (in pixel). Per quanto riguarda invece la risoluzione, questa è inutile: sarà il display del dispositivo a determinarla.
L'immagine è ridimensionata a seconda della dimensione che si vuole mostrare, in quanto i dispositivi con un rapporto di display diverso potrebbero "tagliare" l'immagine fuori dalla visualizzazione.
## Color Image Representation
Per *Spazio dei Colori* (*Color Space*) si intende la definizione tridimensionale per un sistema di colori. Gli attributi del sistema di colore sono mappati attraverso le coordinate spaziali dello spazio del colore.

> [!info] CIE
> Siccome la rappresentazione del colore deve essere indipendente dalla forma di visualizzazione, è stato definito il CIE Reference Color Space. Tutti gli altri spazi di colore sono un sottoinsieme di quest'ultimo

### CIE Color Matching Experiment
![[Pasted image 20250519170648.png]]
### CIE RGB Color Space
Nel 1913 CIE standardizza la RGB Color Matching Functions ottenuta usando tre colori primari monocromatici, corrispondenti alle sensazioni di colore rosso, verde e blu. Queste funzioni mostrano la quantità dei colori primari necessari per ottenere un certo colore ad una certa lunghezza d'onda.
Il CIE RGB Color Space è uno dei tanti spazi di colore, che si distingue per un particolare insieme di colori primari monocromatici.
$$
R=\int_{0}
^\infty I(\lambda)\overline r(\lambda)\ d\lambda
\quad G=\int_{0}
^\infty I(\lambda)\overline g(\lambda)\ d\lambda
\quad R=\int_{0}
^\infty I(\lambda)\overline b(\lambda)\ d\lambda $$
![[Pasted image 20250519172552.png]]
### CIE XYZ Color Space
Per evitare la presenza di valori negativi nelle funzioni CIE RGB matching, è stato sviluppato lo spazio di clori CIE XYZ, in modo tale che le nuove funzioni di color matching siano maggiori o uguali di 0 ovunque.
Il CIE XYZ color space è legato al CIE RGB color space da una trasformazione lineare, strutturata in modo:
- Y è la misura della luminosità di un colore
-  Z è quasi uguale alla stimolazione blu
- X è una combinazione lineare delle tre funzioni di risposta a cono scelte in modo che non siano negative (roughly red)
$$
X=\int E (\lambda)\overline x(\lambda)\ d\lambda\quad Y=\int E (\lambda)\overline y(\lambda)\ d\lambda\quad Z=\int E (\lambda)\overline z(\lambda)\ d\lambda
$$
![[Pasted image 20250519173152.png]]

### CIE xyY Color Space
Dall'usare Y come luminanza si ottiene un risultato utile per ogni valore di Y: il piano XZ conterrà tutte le cromaticità per la data luminanza.
Normalizzando XYZ (ovvero dividendo per X+Y+Z) si ottengono dei valori chiamati x,y,z:
$$
x= \frac{X}{X+Y+Z}\quad y= \frac{Y}{X+Y+Z}\quad z= \frac{Z}{X+Y+Z}= 1-x-y
$$
Siccome $x+y+z=1$, la cromaticità di un colore può essere specificata da soli due parametri x e y (valori normalizzati a partire dai tre iniziali e mappati con il CIE Chromaticity Diagram).
Il *CIE Chromaticity Diagram* rappresenta tutti i colori visibili all'occhio umano, con intensità pari a 1 (il bianco più luminoso supportato dal color display). Il grado di luminanza è espresso dalla cordinata Y tra le XYZ.
