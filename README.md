# numeric-differentiation-Tangent-Lines-Polinomial-

<!DOCTYPE html>
<html>
    
<head>
    <title>Garis Singgung Fungsi Polinomial</title>
    <script>

    function hitung(){
        var a = parseInt(document.getElementById("a").value);
        var b = parseInt(document.getElementById("b").value);
        var c = parseInt(document.getElementById("c").value);
        var d = parseInt(document.getElementById("d").value);
        var e = parseInt(document.getElementById("e").value);
        var x = parseInt(document.getElementById("x").value);
        var fmaju; var fmundur; var df; var tan; var k; var h;

        h = 0.0001
        k = x+h
        l = x-h
        //f(x+h)
        fmaju = (a*(k*k*k*k)) + (b*(k*k*k)) + (c*(k*k)) + (d*k) + e
        //f(x-h)
        fmundur = (a*(l*l*l*l)) + (b*(l*l*l)) + (c*(l*l)) + (d*l) + e
        //f(x)
        fx = (a*(x*x*x*x)) + (b*(x*x*x)) + (c*(x*x)) + (d*x) + e
        // f(x+h)-f(x-h)/2*h
        df = (fmaju - fmundur)/(2*h)
        //Y-Y1 = M(X-X1)
        //Y = M*X - M*X1 + Y1 // MX pisah dibawah, hitung M*X1+Y1
        //Y = Y1 - M*X1
        //Y = fx-(df * x)
        tan = fx-(df * x) 

        // Hasil dari Metode Tengahan
        if(tan < 0){
            // MX = df
            document.getElementById("hasil").innerHTML = " Y = "+df+" x  "+tan+"";
        }

        else if (tan > 0){
            document.getElementById("hasil").innerHTML = " Y = "+df+" x   +  "+tan+"";
        }

        else{
            document.getElementById("hasil").innerHTML = "Masukkan Angka! / Tidak ada Hasil";
            alert("PASTIKAN INPUT BERUPA ANGKA DAN PASTIKAN SEMUA INPUT TERISI");
        }
    }

    </script>
    </head>
<body>
    <div id="tepikiri" class="col-5 container p-1 bg-warning" >
        </div>
    <div class="col-5 container">
    <form style="margin-top: 30px; text-align:center">
    <h1>Garis Singgung Polinomial</h1>
        </form>
    <form   style="margin-top: 10px; text-align:center; border: 3px solid; border-color:#242d4e; background-color:#a7bccf; font:message-box; font-size:x-large;">
    <p>Input Angka pada Fungsi Polinomial di Bawah</p>
    <input type="text" name="a" id="a" style="width:65px ; height: 25px; font-size: x-large; text-align: center;" /> x<sup>4</sup> +
    <input type="text" name="b" id="b" style="width:65px ; height: 25px; font-size: x-large; text-align: center;" /> x<sup>3</sup> +
    <input type="text" name="c" id="c" style="width:65px ; height: 25px; font-size: x-large; text-align: center;" /> x<sup>2</sup> +
    <input type="text" name="d" id="d" style="width:65px ; height: 25px; font-size: x-large; text-align: center;" /> x +
    <input type="text" name="e" id="e" style="width:65px ; height: 25px; font-size: x-large; text-align: center;" /> = 0
        <br/>
        <br/>
        <br/>
    <div>Absis : <input type="text" name="x" id="x" style="width:65px ; height: 25px; font-size: x-large; text-align: center;" />
    </div>
        <br/>
    <button type="button" style="margin-top:30px; width:250px; background-color:#f5ec72; font-size:22px; border-radius:10px" onclick="hitung();"/>Hitung</button>
    <input type = "reset" value = "Clear" style="margin-top:30px; width:250px; background-color:#ffae00; font-size:22px; border-radius:10px">
    <p>Persamaan Garis Singgung adalah:</p>
    <p id="hasil" style="font-size:28px; color: brown;"></p>
        </form>
    <div id="tepikanan" class="col-5 container"></div>

    <form style="margin-top: 10px; text-align:justify; border: 3px solid; background-color:#a7bccf; font:message-box;" ;>
        <h2>Diferensial Numerik</h2>
        <p>Dalam pembahasan kalkulus, kata differensial atau dalam istilah Bahasa Indonesia disebut dengan turunan/diferensiasi merupakan perbandingan perubahan tinggi (selisih tinggi) dan perubahan jarak (selisih jarak). 
            Hal ini terlihat pada persamaan (1), bahwa perbandingan arah y dan arah x dapat didekati dengan pendekatan ax menuju 0 terhadap perbandingan antara selisih perubahan y dan selisih perubahan x.</p>
            <img src="https://latex.codecogs.com/svg.image?\mathit{\frac{dy}{dx}=\displaystyle&space;\lim_{ax&space;\to&space;0}\frac{\Delta&space;y}{\Delta&space;x}}" title="\mathit{\frac{dy}{dx}=\displaystyle \lim_{ax \to 0}\frac{\Delta y}{\Delta x}}" />   (1)
        <p>Pada program di atas kami menggunakan Diferensiasi <strong>Metode Selisih Tengahan</strong> untuk mencari persamaan garis singgung pada fungsi polinomial derajat 4 dengan titik x (absis) tertentu dan nilai <strong>error 0.0001</strong>.</p> 
            Metode selisih tengahan merupakan metode pengambilan perubahan dari dua titik sekitar dari titik yang diukur.</p>

        <div>Berikut Diferensiasi dengan 3 Metode Numerik : </div>
        <p>Metode Selisih Maju</p>
        <img src="https://latex.codecogs.com/svg.image?\mathit{f'(x)=\frac{f(x&plus;h)-f(x)}{h}}" title="\mathit{f'(x)=\frac{f(x+h)-f(x)}{h}}" />
        <p>Metode Selisih Mundur</p>
        <img src="https://latex.codecogs.com/svg.image?\mathit{f'(x)=\frac{f(x)-f(x-h)}{h}}" title="\mathit{f'(x)=\frac{f(x)-f(x-h)}{h}}" />
        <p>Metode Selisih Tengahan</p>
            <img src="https://latex.codecogs.com/svg.image?\mathit{f'(x)=\frac{f(x&plus;h)-f(x-h)}{2h}}" title="\mathit{f'(x)=\frac{f(x+h)-f(x-h)}{2h}}" />
            </form>
    </body>

</html>
