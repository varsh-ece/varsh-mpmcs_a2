## Aim
To Write an assembly language program in 8051 to generate a 250 ms delay using Timer 1 in Mode 1 and blink an LED connected to Port 0.5 continuously.

---

## Apparatus Required
- Personal Computer  
- Keil µVision software  
---

## Algorithm(ASCENDING ORDER)

`````````````````````````````
.

``````````````````````````

## Program (Ascending order)

````````````````````
ORG 0000H

MAIN:
MOV P0,#00H

AGAIN:
CPL P0.5
ACALL DELAY_250MS
SJMP AGAIN

DELAY_250MS:
MOV R2,#05H

DELAY_50MS:
MOV TMOD,#10H
MOV TH1,#03CH
MOV TL1,#0B0H
SETB TR1

LOOP:
JNB TF1,LOOP
CLR TF1
CLR TR1

DJNZ R2,DELAY_50MS
RET
END

````````````````````````````````

## OUTPUT

<img width="1600" height="835" alt="image" src="https://github.com/user-attachments/assets/416dac33-f1ad-4765-80cd-245211122ea4" />

![Uploading image.png…]()



---


## RESULT:
Thus  To Write an assembly language program in 8051 to generate a 250 ms delay using Timer 1 in Mode 1 and blink an LED connected to Port 0.5 continuously is done
