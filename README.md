# ALCP-UCM-TheYorsh
Prácticas para el programa "Maple" con los algoritmos de la evaluación
de la asignatura "Álgebra Computacional" de la UCM, curso 2020-2021.

Basados en la lectura de dos libros:

- Modern Computer Algebra (Joachim von zur Gathen)
- A Computational Introduction to Number Theory and Algebra (Victor Shoup)

Los algoritmos están en .txt para ver los códigos. Para poder aplicarlos hace
falta abrir un archivo .mw y añadirlos línea a línea. La mayoría de los 
algoritmos necesitan que estén cargados todos los algoritmos para
recurrir unos a otros.

Este repositorio ha sido creado con el afán de ampliar el conocimiento sobre 
la asignatura y ver un ejemplo de las técnicas que se pueden aplicar para llegar 
a los resultados de los libros. No se pretende de ninguna manera promover la 
copia literal de los códigos para aprobar la asignatura.

Para ejecutar correctamente los códigos, los ejemplos deberán ir en otro entorno 
de ejecución, es decir, esto no sería correcto:
> InversoFinito:=proc(K,e)
  local inverso, oc, r, s, t, K1, K2;
  oc:=K[Size];
  #termina la función..
  p := 13;
  Zp := Zmod(p);
  InversoFinito(Zp, 5);
  #Lo de arriba es el ejemplo de la función

Sin embargo, esto sí sería correcto:

> InversoFinito:=proc(K,e)
  local inverso, oc, r, s, t, K1, K2;
  oc:=K[Size];
  #termina la función..
  #acabo esta ejecución y creo otra:

> p := 13;
  Zp := Zmod(p);
  InversoFinito(Zp, 5);
  #Lo de arriba es el ejemplo de la función

Los algoritmos son los enumerados a continuación:

**1. Algoritmo de Euclides para cualquier dominio euclideo.**

Dado un dominio euclideo (D.E.) y dos elementos, realiza el Algoritmo de Euclides y
devuelve el m.c.d. de esos elementos.

**2. Algoritmo de Euclides extendido.**

Dado un K D.E. y dos elementos a,b de K, realiza el Algoritmo de Euclides anterior para
devolver el m.c.d. de esos elementos, digamos "d", y encuentra utilizando la 
Identidad de Bezout, los dos números x e y tales que:

a*x + b*y = d

**3. Algoritmo para calcular el Teorema Chino del Resto.**

Sea R un D.E. 
Sean m[0], m[1], ... ,m[r-1] pertenecientes a R coprimos dos a dos
Sean v[0], v[1], ... , v[r-1] pertenecientes a R
Sea m = m[0]*m[1]*...*m[r-1]

Entonces tenemos que m = mcm(m[0],m[1],... m[r-1])

Este teorma dice que existe un elemento f perteneciente a R tal que:

f ≡v[i] mod m[i], para 0 <= i < r

El siguiente algoritmo toma los elementos m[i] y v[i] del enunciado 
y devuelve el mencionado elemento f, utilizando como base la demostración de dicho teorema. 

**4. M.C.D. en un D.F.U.**

Sea K un Dominio de Factorización Única (D.F.U.), y sean f y g dos elementos de K, el 
siguiente algoritmo calcula el Máximo Común Divisor (M.C.D.) entre esos dos elementos
(normalizado). 

**5. Inverso de un elemento en un cuerpo finito.**

Sea K un cuerpo finito, "e" perteneciente a K, el algoritmo devuelve el inverso de "e" en K.
