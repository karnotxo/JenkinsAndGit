fechaNacimiento = "1982-09-18"

pipeline
{
    agent any
    
    stages
    {
        stage("Calcular edad")
        {
            steps
            {
                script 
                {
                    def format = "yyyy-MM-dd"
                    def dateFormat = new java.text.SimpleDateFormat(format)
                    def date = dateFormat.parse(fechaNacimiento)
                    now = new Date();
                    edad = now.getYear() - date.getYear(); // no tenemos en cuenta el dia de nacimiento
                    echo "La edad calculada es ${edad}"
                }
            }
        }
        stage("Generar texto")
        {
            
            steps
            {
                script 
                {
                    def texto = "La edad calculada es ${edad}"
                    writeFile(file: "C:\\data\\development\\edad.txt", text:texto)
                    echo "Fichero escrito"
                }
            }
        }
    }
}
