# Problems for Recitation 1
<https://ocw.mit.edu/courses/6-042j-mathematics-for-computer-science-fall-2010/afcde74688c486d46d3b250326834b04_MIT6_042JF10_rec01.pdf>
## 1 Team Problem: A Mystery

> A certain cabal within the 6.042 course staff is plotting to make the final exam ridiculously hard. ("Problem 1. Prove that the axioms of mathematics are complete and consistent. Express your answer in Mayan hieroglyphics.") The only way to stop their evil plan is to determine exactly who is in the cabal. The course staff consists of nine people:
>
>{Oscar, Stav, Darren, Patrice, David, Nick, Martyna, Marten, Tom}
>
>The cabal is a subset of these nine. A membership roster has been found and appears below, but it is deviously encrypted in logic notation. The predicate incabal indicates who is in the cabal; that is, incabal(x) is true if and only if x is a member. Translate each statement below into English and deduce who is in the cabal.


- (i) $\exists x \exists y \exists z (x \neq y \land x \neq z \land y \neq z \land incabal(x) \land incabal(y) \land incabal(z))$  
There exists at least 3 members in the cabal.
- (ii) $\neg(incabal(Stav) \land incabal(David))$  
At least one of Stav or David is not in the cabal.(Possibly both.)

- (iii) $(incabal(Martyna) \lor incabal(Patrice)) \rightarrow \forall x, incabal(x)$  
If Martyna or(inclusive) Partice is in the cabal, then all nine mebers must be in the cabal.  
Since the right-hand side of the implication is false(ii), the left-hand side must also be false for the statement to hold. Therefore, Neither Martyna nor Partrice is in the cabal.
- (iv) $incabal(Stav) \rightarrow incabal(David)$  
If Stav is in the cabal, then David must also be in the cabal"  
If (iv) is true, and Stav were in the cabal, then David would have to be in the cabal. However, this contradicts statement (ii), which says at least one of them not in the cabal.  
Therefore, Stav is not in the cabal and we still cannot confirm whether David is in the cabal.

- (v) $incabal(Darren) \rightarrow incabal(Martyna)$  
If Darren is in cabal, the Martyna must also be in the cabal.  
If Martyna is not in the cabal, the only way for this implication to hold is for Darren to also be not in the cabal.  
Darren is not in the cabal.

- (vi) $(incabal(Oscar) \lor incabal(Nick)) \rightarrow \neg incabal(Tom)$  
If Oscar or Nick are in the cabal, then Tom is not in the cabal.  
To determine whether this condition holds, we need more information.

- (vii) $(incabal(Oscar) \lor incabal(David)) \rightarrow \neg incabal(Marten)$  
If Oscar or David is in the cabal, then Marten is not in the cabal.  


### Final Conclusions

From our deductions so far:

- Darren, Stav, Martyna, and Partrice are not in the cabal.
- At least three people must be in the cabal  

Thus, the number of possible candidates has been reduced to five:  
{Oscar, David, Nick, Marten, Tom}

#### Case1: Oscar is in the cabal

- From (vi), (vii), both Tom and Marten must be not in the cabal.  
- That leaves David and Nick as the remaining members of the cabal.  

Since we need at least three members, this case is valid.  

#### Case2: Oscar is not in the cabal  

If Oscar is not in the cabal, we need at least three members from {David, Nick, Marten, Tom}.  

- From (vi), if Nick is in the cabal, then Tom must be out.  
- From (vii), if David is in the cabal, then Marten must be out.  
- However, we still need a third member.  
- If you choice Tom and Marten insetead Nick and David, same result: need third member.  

Conclusion:  
Case 1 is the only possible answer. {Oscar, David, Nick}