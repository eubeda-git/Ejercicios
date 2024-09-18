import java.text.SimpleDateFormat
pipeline
{
		agent any
    environment
    {
        fechaNacimiento = "15/09/1945"
        ruta_fichero = "C:\\Cursos\\DevOps\\Ejercicios\\"
        nombre_fichero = "Calcular_edad"
    }
		stages
		{
		  stage("Calcular Edad")
			{
				steps
				{
					script
					{
		 
    		 hoy = new Date()
                formato = new SimpleDateFormat("yyyy")
                    anyoConFormato = formato.format(hoy)				
              
              anyoNacimiento = fechaNacimiento.substring(6)
	      println "ano nacimiento " + anyoNacimiento
		println "ano actual " + anyoConFormato
              def edad = anyoConFormato.toInteger() - anyoNacimiento.toInteger()
              string_edad = "La edad calculada es: " + edad
					}
				}	
			}
      stage("Generar txt")
      {
				steps
				{
					script
					{
				      writeFile(file: "${ruta_fichero}${nombre_fichero}.txt", text:string_edad)
              println("El fichero fue escrito.")
					}
				}	
			}
		}
}
