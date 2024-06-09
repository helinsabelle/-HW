# -HW
https://vscode.dev/profile/github/5095b7bdb3bb8e32fdece73ba8d2fd08


ch3
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>問題</title>
</head>
<body>
    <h1>問題</h1>

    <div id="results"></div>

    <script>
        // 將答案顯示在網頁上
        function displayResult(index, result) {
            const resultElement = document.createElement("p");
            resultElement.textContent = index + ". " + result;
            document.getElementById("results").appendChild(resultElement);
        }

        // (1) 計算2的10次方
        displayResult(1, Math.pow(2, 10));

        // (2) 計算100除以7的商和餘數
        const quotient2 = Math.floor(100 / 7);
        const remainder2 = 100 % 7;
        displayResult(2, "商：" + quotient2 + "，餘數：" + remainder2);

        // (3) 計算10除以3的商，保留2位小數
        displayResult(3, (10 / 3).toFixed(2));

        // (4) 字符串"5"轉換成數字然後乘以10
        displayResult(4, parseFloat("5") * 10);

        // (5) 判斷當前的小時是否大於等於7
        const currentHour = new Date().getHours();
        displayResult(5, "當前小時大於等於7：" + (currentHour >= 7));

        // (6) 將字符串"hello"與字符串"world"連接起來
        displayResult(6, "hello" + "world");

        // (7) 判斷字符串123是否為數字
        displayResult(7, "字符串123是否為數字：" + !isNaN("123"));

        // (8) 判斷字符串"4"轉換成數字之後，是否小於數字"2"
        displayResult(8, parseFloat("4") < 2);

        // (9) 判斷數字15是否在10到20之間（包括10和20）
        displayResult(9, "數字15是否在10到20之間：" + (15 >= 10 && 15 <= 20));

        // (10) 判斷字符串"hello"是否不為undefined且不為null
        displayResult(10, "字符串\"hello\"是否不為undefined且不為null：" + ("hello" !== undefined && "hello" !== null));

        // (11) 將數字25除以2，判斷結果是否為偶數
        displayResult(11, "25除以2的餘數是否為0：" + (25 % 2 === 0));

        // (12) 比較兩個數字x和y的大小
        const x = 10;
        const y = 20;
        displayResult(12, "x和y的比較結果：" + (x > y ? "x 大於 y" : x < y ? "x 小於 y" : "x 等於 y"));
    </script>
</body>
</html>


ch4
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript 練習</title>
</head>
<body>
    <h1>JavaScript 練習</h1>
    <div id="results"></div>
    <script>
        // 將答案顯示在網頁上
        function displayResult(index, result) {
            const resultElement = document.createElement("p");
            resultElement.textContent = index + ". " + result;
            document.getElementById("results").appendChild(resultElement);
        }

        // (1) 提示使用者輸入一個年份，判斷這個年份是否為閏年。
        function isLeapYear(year) {
            if ((year % 4 === 0 && year % 100 !== 0) || (year % 400 === 0)) {
                return true;
            } else {
                return false;
            }
        }
        const year = 2024; // 替換成你要測試的年份
        displayResult(1, `年份 ${year} 是閏年嗎？${isLeapYear(year)}`);

        // (2) 提示使用者輸入一個月份，然後輸出該月份的天數。
        function getDaysInMonth(month, year) {
            switch (month) {
                case 1: case 3: case 5: case 7: case 8: case 10: case 12:
                    return 31;
                case 4: case 6: case 9: case 11:
                    return 30;
                case 2:
                    return isLeapYear(year) ? 29 : 28;
                default:
                    return "無效的月份";
            }
        }
        const month = 2; // 替換成你要測試的月份
        displayResult(2, `月份 ${month} 有 ${getDaysInMonth(month, year)} 天`);

        // (3) 提示使用者輸入一個字串，然後使用 for 迴圈將字串反轉。
        function reverseString(str) {
            let reversed = "";
            for (let i = str.length - 1; i >= 0; i--) {
                reversed += str[i];
            }
            return reversed;
        }
        const str = "hello"; // 替換成你要測試的字串
        displayResult(3, `字串 "${str}" 的反轉結果是 "${reverseString(str)}"`);

        // (4) 使用 for 迴圈印出由 "*" 組成的倒直角三角形。
        function printTriangle(n) {
            let triangle = "";
            for (let i = n; i > 0; i--) {
                triangle += "*".repeat(i) + "\n";
            }
            return triangle;
        }
        const n = 5; // 替換成你要測試的高度
        displayResult(4, `倒直角三角形:\n${printTriangle(n)}`);

        // (5) 使用 while 迴圈判斷一個數是否為質數。
        function isPrime(num) {
            if (num <= 1) return false;
            let i = 2;
            while (i <= Math.sqrt(num)) {
                if (num % i === 0) return false;
                i++;
            }
            return true;
        }
        const num = 17; // 替換成你要測試的數字
        displayResult(5, `數字 ${num} 是質數嗎？${isPrime(num)}`);

        // (6) 使用 while 迴圈印出由 "*" 組成的倒直角三角形。
        function printTriangleWhile(n) {
            let triangle = "";
            let i = n;
            while (i > 0) {
                triangle += "*".repeat(i) + "\n";
                i--;
            }
            return triangle;
        }
        displayResult(6, `倒直角三角形 (使用 while 迴圈):\n${printTriangleWhile(n)}`);

        // (7) 輸入一個正整數 n，使用 do...while 迴圈計算 n! (即 n 的階乘)，並輸出結果。
        function factorial(n) {
            let result = 1;
            let i = 1;
            do {
                result *= i;
                i++;
            } while (i <= n);
            return result;
        }
        const nFactorial = 5; // 替換成你要測試的正整數
        displayResult(7, `數字 ${nFactorial} 的階乘是 ${factorial(nFactorial)}`);

        // (8) 使用 for...of 迴圈找出陣列中的最大值。
        function findMax(arr) {
            let max = arr[0];
            for (const num of arr) {
                if (num > max) max = num;
            }
            return max;
        }
        const arr = [1, 5, 2, 7, 3]; // 替換成你要測試的陣列
        displayResult(8, `陣列 [${arr}] 中的最大值是 ${findMax(arr)}`);

        // (9) 使用 for...of 迴圈計算陣列中所有偶數元素的總和。
        function sumEvenNumbers(arr) {
            let sum = 0;
            for (const num of arr) {
                if (num % 2 === 0) sum += num;
            }
            return sum;
        }
        const arr2 = [1, 2, 3, 4, 5, 6, 7, 8]; // 替換成你要測試的陣列
        displayResult(9, `陣列 [${arr2}] 中偶數元素的總和是 ${sumEvenNumbers(arr2)}`);

        // (10) 使用 for...in 迴圈計算物件中屬性的總和。
        function sumObjectValues(obj) {
            let sum = 0;
            for (const key in obj) {
                sum += obj[key];
            }
            return sum;
        }
        const obj = {a: 1, b: 2, c: 3, d: 4, e: 5}; // 替換成你要測試的物件
        displayResult(10, `物件 {a: 1, b: 2, c: 3, d: 4, e: 5} 中屬性的總和是 ${sumObjectValues(obj)}`);
    </script>
</body>
</html>


ch5
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript 練習</title>
</head>
<body>
    <h1>JavaScript 練習</h1>
    <div id="results"></div>
    <script>
        // 將答案顯示在網頁上
        function displayResult(index, result) {
            const resultElement = document.createElement("p");
            resultElement.textContent = index + ". " + result;
            document.getElementById("results").appendChild(resultElement);
        }

        // 第1張圖片的習題

        // (1) 寫一個函式用來計算任意數字的平均值。
        function average(...nums) {
            let sum = 0;
            for (let num of nums) {
                sum += num;
            }
            return sum / nums.length;
        }
        const nums = [1, 2, 3, 4, 5];
        displayResult(1, `平均值: ${average(...nums)}`);

        // (2) 寫一個函式用來檢查一個數字是否為質數。
        function isPrime(num) {
            if (num <= 1) return false;
            for (let i = 2; i <= Math.sqrt(num); i++) {
                if (num % i === 0) return false;
            }
            return true;
        }
        const numPrime = 7;
        displayResult(2, `數字 ${numPrime} 是質數嗎？${isPrime(numPrime)}`);

        // (3) 寫一個函式用來將一個數字轉換為其二進位表示法的字串。
        function toBinaryString(num) {
            return num.toString(2);
        }
        const numBinary = 10;
        displayResult(3, `數字 ${numBinary} 的二進位表示法是 ${toBinaryString(numBinary)}`);

        // (4) 寫一個函式用來找出陣列中的最小值和最大值。
        function findMinMax(array) {
            let min = array[0], max = array[0];
            for (let i = 1; i < array.length; i++) {
                if (array[i] < min) min = array[i];
                if (array[i] > max) max = array[i];
            }
            return { min, max };
        }
        const arr = [1, 2, 3, 4, 5];
        const { min, max } = findMinMax(arr);
        displayResult(4, `陣列 [${arr}] 中的最小值是 ${min}, 最大值是 ${max}`);

        // 第2張圖片的習題

        // (1) 寫一個遞迴函式用來計算費氏數列的第n項。
        function fibonacci(n) {
            if (n === 1 || n === 2) return 1;
            return fibonacci(n - 1) + fibonacci(n - 2);
        }
        const nFib = 5;
        displayResult(5, `費氏數列的第 ${nFib} 項是 ${fibonacci(nFib)}`);

        // (2) 寫一個遞迴函式用來計算兩個正整數的最大公因數（GCD）。
        function gcd(m, n) {
            if (n === 0) return m;
            return gcd(n, m % n);
        }
        const m = 48, n = 18;
        displayResult(6, `數字 ${m} 和 ${n} 的最大公因數是 ${gcd(m, n)}`);
    </script>
</body>
</html>


ch6
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript 練習</title>
</head>
<body>
    <h1>JavaScript 練習</h1>
    <div id="results"></div>
    <script>
        // 將答案顯示在網頁上
        function displayResult(index, result) {
            const resultElement = document.createElement("p");
            resultElement.textContent = index + ". " + result;
            document.getElementById("results").appendChild(resultElement);
        }

        // 第3張圖片的習題

        // (1) 寫一個函式用來計算一個日期物件現在的天數。
        function getDays(date) {
            const start = new Date(date.getFullYear(), 0, 0);
            const diff = date - start;
            const oneDay = 1000 * 60 * 60 * 24;
            const day = Math.floor(diff / oneDay);
            return day;
        }
        const today = new Date();
        displayResult(1, `今天是今年的第 ${getDays(today)} 天`);

        // (2) 寫一個函式用來將一個字串反轉。
        function reverseString(str) {
            return str.split('').reverse().join('');
        }
        const str = "hello";
        displayResult(2, `字串 "${str}" 反轉後是 "${reverseString(str)}"`);

        // (3) 寫一個函式用來判斷一個字串是否為迴文。
        function isPalindrome(str) {
            let left = 0;
            let right = str.length - 1;
            while (left < right) {
                if (str[left] !== str[right]) {
                    return false;
                }
                left++;
                right--;
            }
            return true;
        }
        const strPalindrome = "racecar";
        displayResult(3, `字串 "${strPalindrome}" 是迴文嗎？${isPalindrome(strPalindrome)}`);

        // (4) 寫一個函式來生成一個指定長度的隨機字串。
        function randomString(length) {
            const chars = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';
            let result = '';
            for (let i = 0; i < length; i++) {
                result += chars.charAt(Math.floor(Math.random() * chars.length));
            }
            return result;
        }
        const length = 10;
        displayResult(4, `隨機字串（長度 ${length}）: ${randomString(length)}`);

        // 第4張圖片的習題

        // (1) 寫一個函式用來判斷一個數字是否為完美數。
        function isPerfectNumber(num) {
            let sum = 0;
            for (let i = 1; i < num; i++) {
                if (num % i === 0) {
                    sum += i;
                }
            }
            return sum === num;
        }
        const numPerfect = 6;
        displayResult(5, `數字 ${numPerfect} 是完美數嗎？${isPerfectNumber(numPerfect)}`);

        // (2) 寫一個函式用來進行氣泡排序法。
        function bubbleSort(arr) {
            var len = arr.length;
            for (var i = 0; i < len; i++) {
                for (var j = 0; j < len - i - 1; j++) {
                    if (arr[j] > arr[j + 1]) {
                        var temp = arr[j];
                        arr[j] = arr[j + 1];
                        arr[j + 1] = temp;
                    }
                }
            }
            return arr;
        }
        const arrBubble = [5, 1, 4, 2, 8];
        displayResult(6, `排序前: [${arrBubble}] 排序後: [${bubbleSort(arrBubble)}]`);
    </script>
</body>
</html>

# -Practice
https://leetcode.com/problem-list/mv4zcp87/ https://www.canva.com/design/DAGB6FpB0Yk/5d-w-DI6heOVJPfzW1Esug/edit
