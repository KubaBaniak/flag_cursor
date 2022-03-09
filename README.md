# flag_cursor
# **Tutorial jak zrobić "kursor-flagę"**

#### 1. Pod znacznikiem **```<body>```** dodajemy element (diva), który będzię naszą flagą poruszającą się po oknie:
  ```
  <div class="flag"></div>
  ```
  
#### 2. W nagłówku **```<head> ... </head>```** dodajemy style do naszego "przyszłego" kursora i ukrywamy stary:
  ```
  * {
      cursor:none;
      pointer-events: none;
  }
  .flag {
      background: linear-gradient(#0057b7 50%, #ffd700 50%);
      width:20px;
      height:20px;
      border-radius: 50%;
      position: fixed;
      left: -100%;
      top: -100%;
    }
  ```
  
#### 3. Zaraz pod znacznikiem **```</body>```** dodajemy skrypt, który śledzi nam pozycję kursora w oknie, i aktualizuje jego pozycję przy każdym ruchu, nadpisując tym samym pozycję wcześniej stworzonego div'a "flagi".

```
<script>
  const cursor = document.querySelector('.flag');
  document.addEventListener('mousemove', (e) => {
    cursor.style.cssText = `left: ${e.clientX}px; top: ${e.clientY}px;`
  })
</script>
```

#### Ostatecznie plik html powinien wyglądać jakoś tak:
```
<!DOCTYPE>
<html>
<head>
<style>
  * {
      cursor:none;
      pointer-events: none;
  }
  .flag {
      background: linear-gradient(#0057b7 50%, #ffd700 50%);
      width:20px;
      height:20px;
      border-radius: 50%;
      position: fixed;
      left: -100%;
      top: -100%;
    }
</style>
</head>

<body>
    <div class="flag"></div>
    <br>
    <br>
    <br>
    <br>
    <br>
    <h1 style="text-align:center">Dużo siły i miłości dla Ukrainy! Jesteśmy z wami.</h1>
</body>
<script>
  const cursor = document.querySelector('.flag');
  document.addEventListener('mousemove', (e) => {
    cursor.style.cssText = `left: ${e.clientX}px; top: ${e.clientY}px;`
  })
</script>
</html>
```


