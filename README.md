## Aim
To Write an assembly language program in 8051 to generate a 250 ms delay using Timer 1 in Mode 1 and blink an LED connected to Port 0.5 continuously.

---

## Apparatus Required
- Personal Computer  
- Keil µVision software  
---

## Algorithm(ASCENDING ORDER)

`````````````````````````````
1.Start program at 0000H.

2.Clear Port 0 → MOV P0,#00H.

3.Repeat forever:

4.Toggle LED at P0.5 → CPL P0.5.

5.Call 250 ms delay subroutine.

6.Delay subroutine (DELAY_250MS):

7.Load R2 = 05H (repeat 5 times for 50 ms × 5 = 250 ms).

8.Set Timer1 in Mode1 → TMOD = 10H.

9.Load Timer1 → TH1=3CH, TL1=B0H.

10.Start Timer → SETB TR1.

11.Wait for overflow → JNB TF1, LOOP.

12.Stop timer, clear flag → CLR TR1, CLR TF1.

13.Decrement R2 and repeat until zero.

14.Return to main loop.

15.End program.

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
