# 1
* The answer to this question can be either 28, if we consider that the 3 groups do not have intersections, or 18, if we consider that those who drink soda and beer are at the intersection.

# 2
* Sarah arrived on time.

# 3
* "Take four and pay for three"

# 4
* She can make 5,040 attempts before she can get Lorenna's phone number right.

# 5

```js
const word = prompt("Enter a word:");
const reverseWord = word.split("").reverse().join("");

if (word === reverseWord) {
  console.log(`${word} is a palindrome!`);
} else {
  console.log(`${word} is not a palindrome.`);
}
```

# 6

```js
function binarySearch(phoneBook, name) {
  let left = 0;
  let right = phoneBook.length - 1;

  while (left <= right) {
    const mid = Math.floor((left + right) / 2);

    if (phoneBook[mid].name === name) {
      return phoneBook[mid].phone;
    } else if (phoneBook[mid].name < name) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }

  return "-";
}

// Example usage:
const phoneBook = [
  { name: "Alice", phone: "123-456-7890" },
  { name: "Bob", phone: "234-567-8901" },
  { name: "Charlie", phone: "345-678-9012" },
  { name: "David", phone: "456-789-0123" },
  { name: "Eve", phone: "567-890-1234" }
];

const name = prompt("Enter a name:");
const phone = binarySearch(phoneBook, name);

if(phone != "-") {
    console.log(`The phone number of ${name} is ${phone}.`);
} else {
    console.log(`Name not found in phone book.`);
}
```

# 3

```sql
SELECT 
    s.SUPPLIER_NAME AS SUPPLIER,
    p.PRICE AS PRICE
FROM 
    SUPPLIER s
INNER JOIN 
    SUPPLY sp ON s.SUPPLIER_CODE = sp.CODE_SUPPLIER
INNER JOIN 
    PART p ON p.CODE_PART = sp.CODE_PIECE
INNER JOIN 
    CAR c ON c.CODE_CAR = sp.CODE_CAR
WHERE 
    s.CITY = 'VITORIA' 
    AND p.NAME_PART = 'MOTOR' 
    AND c.NAME_CAR = 'KOMBI';
```

# 4

```js
function paintBucket(image, x, y, newColor) {
  const originalColor = image[x][y];
  if (originalColor === newColor) {
    // No need to do anything if the new color is the same as the original color
    return;
  }
  const stack = [[x, y]];
  while (stack.length > 0) {
    const [x, y] = stack.pop();
    if (image[x][y] !== originalColor) {
      continue;
    }
    image[x][y] = newColor;
    if (x > 0) {
      stack.push([x - 1, y]);
    }
    if (x < image.length - 1) {
      stack.push([x + 1, y]);
    }
    if (y > 0) {
      stack.push([x, y - 1]);
    }
    if (y < image[0].length - 1) {
      stack.push([x, y + 1]);
    }
  }
}

// Define the image array
const image = [
  ['.','#','#','#','.','.'],
  ['.','#','.','.','#','.'],
  ['.','#','#','#','.','.'],
  ['.','#','.','.','.','.']
];

// Call the paintBucket function with the starting pixel coordinates (0,1) and the new color 'O'
paintBucket(image, 0, 1, 'O');

// Print the modified image to the console
console.log(image);
```
