# Usar la imagen oficial de Java 17 que instalamos denante
FROM eclipse-temurin:17-jdk-alpine

# Crear una carpeta de trabajo dentro del contenedor
WORKDIR /app

# Copiar todos los archivos de tu proyecto al contenedor
COPY . .

# Darle los permisos malditos de Windows y compilar el proyecto
RUN chmod +x mvnw
RUN ./mvnw clean package -DskipTests

# Avisarle a Render que usaremos el puerto 8080
EXPOSE 8080

# El comando final para encender el microservicio
ENTRYPOINT ["sh", "-c", "java -jar target/*.jar"]