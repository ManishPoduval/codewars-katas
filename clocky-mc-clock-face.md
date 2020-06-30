# Clocky Mc Clock-Face

## Story

Due to lack of maintenance the minute-hand has fallen off Town Hall clock face.

And because the local council has lost most of our tax money to a Nigerian email scam there are no funds to fix the clock properly.

Instead, they are asking for volunteer programmers to write some code that tell the time by only looking at the remaining hour-hand!

What a bunch of cheapskates!

Can you do it?

## Kata
Given the `angle` (in degrees) of the hour-hand, return the time in HH:MM format. Round down to the nearest minute.

### Examples

`12:00` = 0 degrees
`03:00` = 90 degrees
`06:00` = 180 degrees
`09:00` = 270 degrees
`12:00` = 360 degrees

#### Notes
0 <= `angle` <= 360


# Solution

```
const whatTimeIsIt = function(angle) {
  // Your code here
  let time= '';
  if (angle == 0) return '12:00'
  
  //every hour is 30deg. If less that 30 then the hr hand corresponds to 12
  
  //formula from https://en.wikipedia.org/wiki/Clock_angle_problem
   
  //every hour corresponds to 30 deg 
  let hrs = angle < 30 ? 12 : ('0' + Math.floor(angle/30)).slice(-2);
  
  //every min corresponds to 6 deg
  let mins = ('0' + Math.floor((angle % 30)*2)).slice(-2);
  return hrs + ':' + mins
}
```
