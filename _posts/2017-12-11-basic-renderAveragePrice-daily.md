---
layout: post
title: "renderAveragePrice.js"
categories: dev
tags: algo
---

#### 객체(object) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

This is a variation of the 'Fashion Inventory' problem.

```javascript
var inventory = [
   {
      name: 'Brunello Cucinelli',
      shoes: [
         { name: 'tasselled black', price: 1000 },
         { name: 'tasselled green', price: 1100 },
         { name: 'plain beige', price: 950 },
         { name: 'plain olive', price: 1050 }
      ]
   },
   {
      name: 'Gucci',
      shoes: [
         { name: 'red leather sneakers', price: 800 },
         { name: 'black leather sneakers', price: 900 }
      ]
   }
];
```

<br>

Now output the average cost of all shoes per designer in this format:

```javascript
var expected = {
   'designers': [
      {
         'name': 'Brunello Cucinelli',
         'averagePrice': 1025
      },
      {
         'name': 'Gucci',
         'averagePrice': 850
      }
   ]
};
```

<br>

## solution

```javascript
function renderAveragePrice(inventory) {
   let result = { designers: [] };
   
   for (let i = 0; i < inventory.length; i++) {
      let item = inventory[i];
      let designer = { name: item.name, averagePrice: 0 };
      let sum = 0;
      
      for (let j = 0; j < item.shoes.length; j++) {
         sum += item.shoes[j].price;
      }
      designer.averagePrice = sum / item.shoes.length;
      result.designers.push(designer);
   }
   return result;
}


renderAveragePrice(inventory);
//	{ designers:
//	[
//		{ name: 'Brunello Cucinelli', averagePrice: 1025 },
//		{ name: 'Gucci', averagePrice: 850 }
//	]
//	}
```

