# Math in WebSharper

Higher level math is supported in WebSharper via the [MathJS](http://mathjs.org/) and [MathJax](https://www.mathjax.org/) JavaScript libraries.

## Bignumbers

F# already supports BigInteger (System.Numerics.BigInteger or bigint), but JavaScript does not by default. With WebSharper the usage of these types and their operators are just as easy as working with integers.

Constructing BigInteger has two ways

    open System.Numerics
    open WebSharper.MathJS
    
    //The .Net way
    let myBignum = bigint 100
    
    //A new way
    let myBignumFromString = Math.Bignumber("100")

<div style="width:100%;min-height:500px;position:relative"><iframe style="position:absolute;border:none;width:100%;height:100%;overflow:hidden" src="http://test2.try.websharper.com/embed/setr/0000DE"></iframe><div>

---

## Complex number

Just like BigInteger, Complex is a member of System.Numerics too, but JavaScript does not support them. The Complex type got a new contructor too:

    open System.Numerics
    open WebSharper.MathJS
    
    //The .Net way
    let myComplex = Complex(1., 1.)
    
    //A new way
    let myComplexFromString = Math.Complex("1 + 1i")

<div style="width:100%;min-height:500px;position:relative"><iframe style="position:absolute;border:none;width:100%;height:100%" src="http://test2.try.websharper.com/embed/setr/0000DH"></iframe><div>

---

## Fraction

The original float type in JavaScript has limitations with its precision, but it's solved with the Fraction type which has a much higher precision with its operations.

We have many ways to create a Fraction, for example:

    open WebSharper.MathJS
    
    //From string
    let fraction1 = Math.Fraction("1/2")
    
    //By giving the numerator and denominator
    let fraction2 = Math.Fraction(1, 2)
    
    //From float
    let fraction3 = Math.Fraction(0.5)

<div style="width:100%;min-height:500px;position:relative"><iframe style="position:absolute;border:none;width:100%;height:100%" src="http://test2.try.websharper.com/embed/setr/0000DJ"></iframe><div>

---

## Vectors

For vector operations in WebSharper we have to use the MathJS.Math functions and needs the MathNumber wrapper.

    open WebSharper.MathJS

    let myVector = [| 1.; 2.; 3. |]
    
    let addVector = Math.Add(MathNumber(myVector), MathNumber(myVector))

<div style="width:100%;min-height:300px;position:relative"><iframe style="position:absolute;border:none;width:100%;height:100%" src="http://test2.try.websharper.com/embed/setr/0000Di"></iframe><div>

---

## Matrices

The same as for vectors, WebSharper grants a huge variety of Matrix operations and functions, but to use those, we need to wrap the matrix in MathNumber.

    open WebSharper.MathJS
    
    let myMatrix = [| [| 1.; 2. |]; [| 3.; 4. |] |]
    
    let addMatrix = Math.Add(MathNumber(myMatrix))

<div style="width:100%;min-height:300px;position:relative"><iframe style="position:absolute;border:none;width:100%;height:100%" src="http://test2.try.websharper.com/embed/setr/0000DM"></iframe><div>

---

## Units

WebSharper allows you to calculate with units too. Creating Unit are easy too:

    open WebSharper.MathJS
    
    //With a value and a unit
    let myUnit = MathUnit(5, "cm")
    
    //Or simply by a string
    let myUnitFromString = MathUnit("5 cm")

<div style="width:100%;min-height:500px;position:relative"><iframe style="position:absolute;border:none;width:100%;height:100%" src="http://test2.try.websharper.com/embed/setr/0000DO"></iframe><div>