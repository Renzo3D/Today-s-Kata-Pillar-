# Today-s-Kata-Pillar-


This is a level 8 kata

instructions of train kata.

There are pillars near the road. The distance between the pillars is the same and the width of the pillars is the same. Your function accepts three arguments:

1- number of pillars (≥ 1);


2- distance between pillars (10 - 30 meters);



3- width of the pillar (10 - 50 centimeters).
Calculate the distance between the first and the last pillar in centimeters (without the width of the first and last pillar).


This is how I approach to this problem. 

 ONE PILLAR .- there is no distance between pillars because there is only one, So, total distance = 0
 
 
 TWO PILLARS .- here we have to take in consideration the following hint (without the width of the first and last pillar)
                with two pillars we have first and last pillars, so it only counts the distance IN CENTIMETERs.
                
                
THREE AND MORE PILLARS.- here is when we have to do some logic. I a graphic person so I am going to graph a couple of pillars and give you my logic.



  number of pillars 5, ditance bwt 10m and width 15cm  
  
  |    10m      |     10m      |     10m        |    10m       |   
        (without the width of the first and last pillar)
 0cm          15cm           15cm              15cm           0cm
 
 
 can you see something? 
 
 if number of pillars is 5 that means there are 4 distance in between pillars and 3 width dimension in consideration BECAUSE(without the width of the first and last pillar) 
 
With this gold in mind we can say that whatever number of pillars we are giving we will have #pillars - 1 of distance btw pillars; and #pillars -2 of width 


Other EXAMPLE: 

11 pillars - 10m ditance btw - 15cm width 

distance = distance * 100 ( to convert to cm)

11 pillars = |  dist    |w  dist    w|  dist    |w  dist    w|  dist    |w  dist    w|  dist    |w  dist    w|  dist    w|  dist    |

this makes 10 DIST and 9 WIDTH


Now lets code it...


function pillars(num_pill, dist, width) {

  dist = dist*100

  if (num_pill <= 1) {
    return 0
  }
  
  if (num_pill == 2) {
    return dist
  }
  
  if (num_pill >= 3) {
    
    dist = dist * (num_pill - 1)
    width = width *(num_pill - 2)
    var total = dist + width
    return total 
  
  }
  
}

 If it is not clear enough please just shot me a message and I will try to clarify this to detail.
 I am sharing some others people smartest soutions in case you want more complex code. Thanks.
\\


function pillars(num_pill, dist, width) {
  // your code here
  return num_pill>1?(num_pill-1)*dist*100+(num_pill-2)*width:0;
}

function pillars(num_pill, dist, width) {
  return num_pill <= 1 ? 0 : (num_pill - 1) * dist * 100 + (num_pill - 2) * width;
}

const pillars = (n, d, w) => Math.max(0, n - 1) * (d * 100) + Math.max(0, n - 2) * w; 


USEFUL INFORMATION DESCRIBING QUESTION MARK '?' and COLON ':' 

'condition' ? 'value-if-true' : 'value-if-false'
Think of the ? as "then" and : as "else".

hsb.s = max != 0 ? 255 * delta / max : 0;

equivalent to

if (max != 0)
  hsb.s = 255 * delta / max;
else
  hsb.s = 0;



  
