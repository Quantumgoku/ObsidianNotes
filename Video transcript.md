---
created: 2026-08-23T20:01
updated: 2026-10-12T22:08
---
int x=10;
when we write this what does it mean?
matlab like int pta h data type h, x variable h and 10 us variable ka value right?
lekin hum puche ki machine me like computer me 10 kaha store hua? x kya h processor ko pta nhi h angreji x kya h? pointers kya h? agar koi thoda aage h to...... uske liye bhi ki bc pointer address hi kahe store karta h wo bhi to container hi h na 1 type se????

hmmm to is video me hum try karenge memory ko scratch se build karne ka logical pov se not hardware kasam se hardware flip flops mil jata to hum jarur try to karte khair choro.

ee video me stack heap address cover karenge i hope smjha paye sexy tarike se.

ab dekho jab int x=10 likhe or save karke compile kiye gcc ya koi bhi compiler se. to gcc tumhara ye code ko assembly me convert karke 1 executable bna deta right and then fir usko tum run karoge to cpu tumhara instruction by instruction execute karega 
fetch->decode->execute yahi hota cpu ka. but ye to instruction hue na humko chaiye data store kaha hua.

wu hota in memory no new baat, ab mem bahute prakar ke hote ram,storage,l1 l2 cache, etc......



| 0x000 |     |
| ----- | --- |
| 0x001 |     |
| 0x002 |     |
| 0x003 |     |
| ...   |     |
manke chalo har 1 block 4 byte ka data store karskta data idhar mane bits 0 1, kahe ki memory jo h wu kuch nhi transistor h ghanta nhi pta usko ki jo store kar rhe wo string h number usko bas malum on off. ma kasam jab tumlog hardware implementation dekhoge memory ya storage ka maja aajaega ki insan kya hi bna diya.... choro

ab scene ye h ki jo compiler h, matlab jab tum assembly me code karoge or tumko variable store karna hoga kaha store karoge waha na sections hote h jo tum 1 file ka code likha h wo bahut sections me tut jata .data section .bss section .text
ab kya h na ki intialized or uninitialized ka bhi scene hota kahe ki .data section me jitne bhi initialized variable h unko store karte kaise karenge aise

.data
	x dd 10
 ee likhe ab jo assembler h wo 2 baar read karega phla pass me 1 symbol table create karta assembler or har 1 label ko 1 offset se attach karta offset means offset from start of memory segment. jab code run hota to OS us process ko memory deta h work karne ko usko hi data segment bolte or uska starting se offset milta alag alag label ko

ab kya hoga sexy cheez ki dusra pass hoga assembler is pass me wo kya karega jaha jaha ye label likha h waha memory address likh dega