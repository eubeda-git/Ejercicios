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
				    
              def anyo = new Date().getYear()
              anyoNacimiento = fechaNacimiento.substring(6)
	      println "ano nacimiento " + anyoNacimiento
		println "ano actual " + anyo
              def edad = anyo.toInteger() - anyoNacimiento.toInteger()
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
