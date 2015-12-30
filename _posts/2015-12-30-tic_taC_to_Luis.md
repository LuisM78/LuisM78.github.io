

```python
from IPython.display import clear_output
```


```python
import time

```


```python
boardt = '_|_|_'
```


```python
boardm='_|_|_'
```


```python
boardb = ' | | '
```


```python
print boardt
print boardm
print boardb
```

    _|_|_
    _|_|_
     | | 
    


```python
def player_move(player,inde):
    global boardt,boardm,boardb
    if inde == 1 and boardt[0]=='_':
        lt = list(boardt)
        lt[0]=str(player)
        boardt = ''.join(lt)
    if inde == 2 and boardt[2]=='_':
        lt = list(boardt)
        lt[2]=str(player)
        boardt = ''.join(lt)
    if inde == 3 and boardt[4]=='_':
        lt = list(boardt)
        lt[4]=str(player)
        boardt = ''.join(lt) 
    if inde == 4 and boardm[0]=='_':
        lt = list(boardm)
        lt[0]=str(player)
        boardm = ''.join(lt)
    if inde == 5 and boardm[2]=='_':
        lt = list(boardm)
        lt[2]=str(player)
        boardm = ''.join(lt) 
    if inde == 6 and boardm[4]=='_':
        lt = list(boardm)
        lt[4]=str(player)
        boardm = ''.join(lt)  
    if inde == 7 and boardb[0]==' ':
        lt = list(boardb)
        lt[0]=str(player)
        boardb = ''.join(lt)
    if inde == 8 and boardb[2]==' ':
        lt = list(boardb)
        lt[2]=str(player)
        boardb = ''.join(lt) 
    if inde == 9 and boardb[4]==' ':
        lt = list(boardb)
        lt[4]=str(player)
        boardb = ''.join(lt)    
        
        
    pbrd()

def pbrd():
    print 'Select the corresponding location by typing the number'
    print 
    print 'On the left board game'
    print boardt + '                    1|2|3'  
    print boardm + '                    4|5|6'  
    print boardb + '                    7|8|9'  
    

def selectplayer():
    pbrd()
    print 'Please select a player number, 0 or 1 (only those two options)'
    player1 =input()
    if player1 ==0:
        player2 = 1
    if player1 ==1:
        player2 = 0
    print ' Player 1 is: ' , player1
    print ' Player 2 is: ' , player2
    
    i = range(1,10)
    print i
    
    for move in i:
        
        print "select your index"
        
        if move%2 == 0:
            time.sleep(0.25)
            clear_output()
            pbrd()
            print "Right now the player is: ", player1
            index=input()
            player_move(player1,index)
            
            clear_output()
            
        if move%2 == 1:
            time.sleep(0.25)
            clear_output()
            pbrd()
            print "Right now the player is: ", player2
            index=input()
            player_move(player2,index)
            
        a=False    
        a = checkwins()    
        if a==True:
            pbrd()
            clearboard()
            break
        
```


```python
print boardt
```

    _|_|_
    


```python
print boardm
```

    _|_|_
    


```python
print boardb
```

     | | 
    


```python
#lt1 = list(boardt)
#lt1[0]='0'
#lt1[2]='0'
#lt1[4]='0'
#boardt=''.join(lt1)





```


```python
def checkwins():
    if list(boardt)[0]=='1' and list(boardt)[2]=='1' and list(boardt)[4]=='1':
        clear_output()
        print '***************************************'
        print 'Player with "1" wins!', 'First top row' 
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardm)[0]=='1' and list(boardm)[2]=='1' and list(boardm)[4]=='1':
        clear_output()
        print '***************************************'
        print 'player with "1" wins!' , 'Middle row'
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardb)[0]=='1' and list(boardb)[2]=='1' and list(boardb)[4]=='1':
        clear_output()
        print 'player with "1" wins!', 'Bottom row'
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardt)[0]=='1' and list(boardm)[0]=='1' and list(boardb)[0]=='1':
        clear_output()
        print 'player with "1" wins!', 'First column'  
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardt)[2]=='1' and list(boardm)[2]=='1' and list(boardb)[2]=='1':
        clear_output()
        print 'player with "1" wins!' , 'Second Column'
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardt)[4]=='1' and list(boardm)[4]=='1' and list(boardb)[4]=='1':
        clear_output()
        print 'player with "1" wins!', 'Third Column'
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardt)[0]=='1' and list(boardm)[2]=='1' and list(boardb)[4]=='1':
        clear_output()
        print 'player with "1" wins!', 'Diagonal top to bottom'
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardt)[4]=='1' and list(boardm)[2]=='1' and list(boardb)[0]=='1':
        clear_output()
        print 'player with "1" wins!', 'Diagonal bottom to bottom'
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardt)[0]=='0' and list(boardt)[2]=='0' and list(boardt)[4]=='0':
        clear_output()
        print 'player with "0" wins!', 'First top row'
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardm)[0]=='0' and list(boardm)[2]=='0' and list(boardm)[4]=='0':
        clear_output()
        print 'player with "0" wins!' , 'Middle row'
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardb)[0]=='0' and list(boardb)[2]=='0' and list(boardb)[4]=='0':
        clear_output()
        print 'player with "0" wins!', 'Bottom row'
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardt)[0]=='0' and list(boardm)[0]=='0' and list(boardb)[0]=='0':
        clear_output()
        print 'player with "0" wins!', 'First column'
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardt)[2]=='0' and list(boardm)[2]=='0' and list(boardb)[2]=='0':
        clear_output()
        print 'player with "0" wins!' , 'Second Column'
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardt)[4]=='0' and list(boardm)[4]=='0' and list(boardb)[4]=='0':
        clear_output()
        print 'player with "0" wins!', 'Third Column'
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardt)[0]=='0' and list(boardm)[2]=='0' and list(boardb)[4]=='0':
        clear_output()
        print 'player with "0" wins!', 'Diagonal top to bottom'
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)
    if list(boardt)[4]=='0' and list(boardm)[2]=='0' and list(boardb)[0]=='0':
        clear_output()
        print 'player with "0" wins!', 'Diagonal bottom to bottom'
        print '**************************************'
        print 'Run again the cell to play again'
        print 
        return(True)

```


```python
def clearboard():
    global boardt,boardm,boardb
    boardt = '_|_|_'
    boardm = '_|_|_'
    boardb = ' | | '
    

```


```python
selectplayer()
```

    player with "1" wins! Diagonal top to bottom
    **************************************
    Run again the cell to play again
    
    Select the corresponding location by typing the number
    
    On the left board game
    1|_|0                    1|2|3
    _|1|0                    4|5|6
     | |1                    7|8|9
    


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```
