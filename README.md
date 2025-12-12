<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="utf-8" />
  <title>Простые решения — циклы (без var/let/const)</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; }
    button { display:block; margin:8px 0; padding:8px 12px; }
  </style>
</head>
<body>
  <h3>Простые решения (не используем var/let/const)</h3>

  <button onclick="powerWhile()">WHILE: степень</button>
  <button onclick="factorialWhile()">WHILE: факториал</button>
  <button onclick="divideDoWhile()">DO...WHILE: делим 1000 на 2</button>
  <button onclick="multiplesFor()">FOR: кратные 1..100</button>
  <button onclick="primeCheck()">Практическое: простое?</button>

<script>
function powerWhile(){
  // b и e — без объявления (простая школа)
  b = prompt("Основание (число):");
  if (b === null) return;
  e = prompt("Степень (целое >=0):");
  if (e === null) return;
  b = Number(b);
  e = parseInt(e, 10);
  res = 1;
  i = 0;
  while (i < e){
    res = res * b;
    i = i + 1;
  }
  alert(b + " ^ " + e + " = " + res);
}

function factorialWhile(){
  n = prompt("Число для факториала (целое >=0):");
  if (n === null) return;
  n = parseInt(n, 10);
  res = 1;
  i = 1;
  while (i <= n){
    res = res * i;
    i = i + 1;
  }
  alert(n + "! = " + res);
}

function divideDoWhile(){
  v = 1000;
  cnt = 0;
  do {
    v = v / 2;
    cnt = cnt + 1;
  } while (v >= 50);
  alert("Осталось: " + v + "\nДелений: " + cnt);
}

function multiplesFor(){
  d = prompt("Введите делитель (целое, не 0):");
  if (d === null) return;
  d = parseInt(d, 10);
  out = "";
  first = true;
  for (i = 1; i <= 100; i = i + 1){
    if (i % d === 0){
      if (first){
        out = out + i;
        first = false;
      } else {
        out = out + ", " + i;
      }
    }
  }
  if (out === "") out = "Нет чисел, кратных " + d;
  alert("Кратные " + d + ":\n" + out);
}

function primeCheck(){
  n = prompt("Проверить число на простоту (целое >1):");
  if (n === null) return;
  n = parseInt(n, 10);
  if (n <= 1){
    alert("Число должно быть > 1");
    return;
  }
  isPrime = true;
  for (i = 2; i < n; i = i + 1){
    if (n % i === 0){
      isPrime = false;
      break;
    }
  }
  if (isPrime){
    alert(n + " — простое");
  } else {
    alert(n + " — не простое");
  }
}
</script>
</body>
</html>
