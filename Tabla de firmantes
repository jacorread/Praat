# Autor: Laboratorio de Fonética de la Facultad de Letras,Pontificia Universidad Católica de Chile
# Adaptado por: José Alejandro Correa, 2014


clearinfo 
# Presenta el formulario para los datos del informante 
form Parámetros
	natural nivel 1 
	natural rango 5500
	comment En nivel se indica el número del tier de puntos con las respectivas marcas 
endform 
# Asigna distintos valores dependiendo del sexo del informante
# para crear el objeto Formant y luego obtener los valores 



# Imprime una línea de títulos de columnas 
printline Caso'tab$'Tiempo
...'tab$'Vocal'tab$'F1'tab$'b1'tab$'F2'tab$'b2 
# Selecciona el objeto Sound y crea el objeto Formant 
sonido$ = selected$ ("Sound")
select Sound 'sonido$'
To Formant (burg)... 0 5 'rango' 0.025 50
# En el TextGrid, busca el número de marcas, y las etiquetas existentes.
# En el objeto Formant encuentra los valores para
# F1, F2, b1, b2 para cada punto 
# Imprime los datos en la pantalla.
select TextGrid 'sonido$'
ndepunto = Get number of points... 'nivel'

for i to ndepunto
	select TextGrid 'sonido$'
	tiempopunto = Get time of point... 'nivel' 'i'
	etiquetapunto$ = Get label of point... 'nivel' 'i'
	# seleccionar objeto formantes 
	select Formant 'sonido$'
	f1 = Get value at time... 1 'tiempopunto' Hertz Linear
	b1 = Get bandwidth at time... 1 'tiempopunto' Hertz Linear
	f2 = Get value at time... 2 'tiempopunto' Hertz Linear
	b2 = Get bandwidth at time... 2 'tiempopunto' Hertz Linear
		printline 'i''tab$''tiempopunto:2''tab$'
	...'etiquetapunto$''tab$''f1:0''tab$''b1:0''tab$''f2:0''tab$''b2:0''tab$'
endfor 
# Selecciona el objeto Formant y lo borra 
select Formant 'sonido$'
Remove
