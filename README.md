# assignment
////////////////////////////////////////////////////////////1
var num=12345;
var reverse=0;
while(num!=0){
reverse=(reverse*10)+(num%10);
num=parseInt(num/10);
}
alert(num);
////////////////////////////////////////////////////////////2.
function check_Palindrome(str_entry){

   var cstr = str_entry.toLowerCase().replace(/[^a-zA-Z0-9]+/g,'');
	var ccount = 0;

	if(cstr==="") {
		console.log("Nothing found!");
		return false;
	}

	if ((cstr.length) % 2 === 0) {
		ccount = (cstr.length) / 2;
	} else {

		if (cstr.length === 1) {
			console.log("Entry is a palindrome.");
			return true;
		} else {

			ccount = (cstr.length - 1) / 2;
		}
	}

	for (var x = 0; x < ccount; x++) {
		if (cstr[x] != cstr.slice(-1-x)[0]) {
			console.log("Entry is not a palindrome.");
			return false;
		}
	}
	console.log("The entry is a palindrome.");
	return true;
}
check_Palindrome('level');

////////////////////////////////////////////////////////////3.

let stringCombinations = (str) => {
  let strLength = str.length;
  let result = [];
  let currentIndex = 0;
  while (currentIndex < strLength) {
    let char = str.charAt(currentIndex);
    let x;
    let arrTemp = [char];
    for (x in result) {
      arrTemp.push("" + result[x] + char);
    }
    result = result.concat(arrTemp);
    currentIndex++;
  }
  return result;
};
console.log(stringCombinations("dog"));

////////////////////////////////////////////////////////////4.
function alphabet_order(str)
  {
return str.split('').sort().join('');
  }
console.log(alphabet_order("typewriter"));
////////////////////////////////////////////////////////////5.
function uppercase(str)
{
  var array1 = str.split(' ');
  var newarray1 = [];
    
  for(var x = 0; x < array1.length; x++){
      newarray1.push(array1[x].charAt(0).toUpperCase()+array1[x].slice(1));
  }
  return newarray1.join(' ');
}
console.log(uppercase("There is no god except Allah"));
////////////////////////////////////////////////////////////6.
function longfinder(word)
{
  var arr = word.match(/\w[a-z]{0,}/gi);
  var result = arr[0];

  for(var x = 1 ; x < arr.length ; x++)
  {
    if(result.length < arr[x].length)
    {
    result = arr[x];
    } 
  }
  return result;
}
console.log(longfinder('Web Development Tutorial'));
///////////////////////////////////////////////////////////7.
function counter(str1)
{
  var vowel_list = 'aeiouAEIOU';
  var vcount = 0;
  
  for(var x = 0; x < str1.length ; x++)
  {
    if (vowel_list.indexOf(str1[x]) !== -1)
    {
      vcount += 1;
    }
  
  }
  return vcount;
}
console.log(counter("a man went to the woods"));
//////////////////////////////////////////////////////////8.
function check(n)
{

  if (n===1)
  {
    return false;
  }
  else if(n === 2)
  {
    return true;
  }else
  {
    for(var x = 2; x < n; x++)
    {
      if(n % x === 0)
      {
        return false;
      }
    }
    return true;  
  }
}

console.log(check(37));
///////////////////////////////////////////9.
function detect_data_type(value)
{
var dtypes = [Function, RegExp, Number, String, Boolean, Object], x, len;
    
if (typeof value === "object" || typeof value === "function") 
    {
     for (x = 0, len = dtypes.length; x < len; x++) 
     {
            if (value instanceof dtypes[x])
            {
                return dtypes[x];
            }
      }
    }
    
    return typeof value;
}
console.log(detect_data_type(12));
////////////////////////////////////////////////////////10.
function Second_Greatest_Lowest(arr_num)
{
  arr_num.sort(function(x,y)
           {
           return x-y;
           });
  var uniqa = [arr_num[0]];
  var result = [];
  
  for(var j=1; j < arr_num.length; j++)
  {
    if(arr_num[j-1] !== arr_num[j])
    {
      uniqa.push(arr_num[j]);
    }
  }
    result.push(uniqa[1],uniqa[uniqa.length-2]);
  return result.join(',');
  }

console.log(Second_Greatest_Lowest([1,2,3,4,5]));
