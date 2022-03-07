# flag_cursor
# **Tutorial jak zrobić "kursor-flagę"**

#### 1. Pod znacznikiem **```<body>```** dodajemy element (diva), który będzię naszą flagą poruszającą się po oknie:
  ```
  <div class="flag"></div>
  ```
  
#### 2. W nagłówku **```<head> ... </head>```** dodajemy style do naszego "przyszłego" nowego kursora i ukrywamy stary:
  ```
  * {
      cursor:none;
  }
  .flag {
      background: linear-gradient(#0057b7 50%, #ffd700 50%);
      width:75px;
      height:50px;
      position: fixed;
      transform: translate(-50%, -50%);
      left: 50%;
      top: 50%;
      pointer-events: none;
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
