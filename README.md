# Assignment2_Maddelavedu
# Pravallika Maddelavedu
###### Araku Valley/Vishakhapatnam

Araku Valley is a **hill station** and valley region in the southeastern Indian state of Andhra Pradesh. It's surrounded by the thick forests of the Eastern Ghats mountain range. The **Tribal Museum** is dedicated to the area's numerous indigenous tribes, known for their traditional Dhimsa dance, and showcases traditional handicrafts. A miniature train runs through Padmapuram Gardens, with its sculptures and tree-top huts.
Araku Valley is also **famous for its rich coffee plantations**.

***
### Way to My Favorite Place
***

1. Go to kansas Airport
2. Book A Ticket To Vizag
      1. Go To Araku
1. Come Back To Airport
2. After That Come Back To Maryville      
 
***
 ### Items to Carry(Unordered)
***

* Mobile Phone Is Mandatory
* Essential Items Required For Travelling
     * Camera
     * Food
     * Trekking

*** 
### Regarding Myself_Maddelavedu Pravallika     
***
[click Here](https://github.com/MPravallika6/Assignment2_Maddelavedu/blob/main/AboutMe.md)

***
### Referred food
***

In This Table I going to Share about foods items which i have tasted near maryville. Chuys Mexican Food which is in kansas city i like to prefer chicka-chicka boom-boom, Panchos also good in taste and delicious. Taco Bell is in Missouri My favorite food is chicken chipotle melt and chicken quesadilla. I would suggest everyone to try these.

| Food                                | Location | Price  |
|-------------------------------------|----------|--------|
| Panchos                             | Kansas   | $12.98 |    
| chicka-chicko boom-boom enchiladas  | Kansas   | $11.89 |    
| chicken chipotle                    | Missouri | $1     |
| chicken quesadila                   | Missouri | $4.49  |

***
### Quotes
***

>"Keep away from people who try to belittle your ambitions. Small people always do that, but the really great make you feel that you, too, can become great."
***MARK TWAIN***.

>"Fastasy is hardly an escape from reality. It's a way of understanding it."
***LLOYD LEXANDER***.

***
### code Fencing - Lexicographical Next Balanced Sequence
***

>First find the rightmost opening bracket which we can replace it by a closing bracket to get the lexicographically larger bracket string. The updated string might not be balanced, we can fill the remaining part of the string with the lexicographically minimal one: i.e. first with as much opening brackets as possible, and then fill up the remaining positions with closing brackets. In other words we try to leave a long as possible prefix unchanged, and the suffix gets replaced by the lexicographically minimal one.To find this position, we can iterate over the character from right to left, and maintain the balance depth of open and closing brackets. When we meet an opening brackets, we will decrement depth, and when we meet a closing bracket, we increase it. If we are at some point meet an opening bracket, and the balance after processing this symbol is positive, then we have found the rightmost position that we can change. We change the symbol, compute the number of opening and closing brackets that we have to add to the right side, and arrange them in the lexicographically minimal way.

[ForMoreInformation](https://cp-algorithms.com/)

```
bool next_balanced_sequence(string & s) {
    int n = s.size();
    int depth = 0;
    for (int i = n - 1; i >= 0; i--) {
        if (s[i] == '(')
            depth--;
        else
            depth++;

        if (s[i] == '(' && depth > 0) {
            depth--;
            int open = (n - i - 1 - depth) / 2;
            int close = n - i - 1 - open;
            string next = s.substr(0, i) + ')' + string(open, '(') + string(close, ')');
            s.swap(next);
            return true;
        }
    }
    return false;
}
```
[ForMoreInformation](https://cp-algorithms.com/combinatorics/bracket_sequences.html)