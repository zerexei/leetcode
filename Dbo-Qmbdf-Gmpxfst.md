```ts
function canPlaceFlowers(flowerbed: number[], n: number): boolean {
    // const canPlants = flowerbed.filter((v, i) => {
    //     if (i % 2) return false;
    //     if (v) return false
    //     return String(v);
    // })

    // return canPlants.length >= n;

    // [1,0,0,0,0,1] 
    // [1,0,1,0,0,1] - 2
    // [1,0,0,0,0,1] - 4

    let count = 0;
    let i = 0;
    const len = flowerbed.length;

    while (i < len) {
        if (
            flowerbed[i] === 0 &&
            (i === 0 || flowerbed[i - 1] === 0) &&
            (i === len - 1 || flowerbed[i + 1] === 0)
        ) {
            count++;
            i += 2;
        } else {
            i += flowerbed[i] === 1 ? 2 : 1;
        }

        if (count >= n) return true;
    }

    return false;
};
```


# 605. Can Place Flowers
You have a long flowerbed in which some of the plots are planted, and some are not. However, flowers cannot be planted in adjacent plots.

Given an integer array flowerbed containing 0's and 1's, where 0 means empty and 1 means not empty, and an integer n, return true if n new flowers can be planted in the flowerbed without violating the no-adjacent-flowers rule and false otherwise.

 

Example 1:

Input: flowerbed = [1,0,0,0,1], n = 1
Output: true
Example 2:

Input: flowerbed = [1,0,0,0,1], n = 2
Output: false
 

Constraints:

1 <= flowerbed.length <= 2 * 104
flowerbed[i] is 0 or 1.
There are no two adjacent flowers in flowerbed.
0 <= n <= flowerbed.length
