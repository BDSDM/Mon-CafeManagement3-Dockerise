# Étape 1 : Build de l'application.
FROM maven:3.8.5-openjdk-17 AS build
WORKDIR /app

# Copier uniquement les fichiers nécessaires en priorité pour le cache Docker
COPY pom.xml .
COPY src ./src

# Résolution des dépendances et compilation (on skip les tests)
RUN mvn clean package -DskipTests

# Étape 2 : Image d'exécution
FROM openjdk:17
WORKDIR /app
COPY --from=build /app/target/*.jar app.jar

EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
# Étape 1 : Build de l'application
FROM maven:3.8.5-openjdk-17 AS build
WORKDIR /app

# Copier uniquement les fichiers nécessaires en priorité pour le cache Docker
COPY pom.xml .
COPY src ./src

# Résolution des dépendances et compilation (on skip les tests)
RUN mvn clean package -DskipTests

# Étape 2 : Image d'exécution
FROM openjdk:17
WORKDIR /app
COPY --from=build /app/target/*.jar app.jar

EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
# Étape 1 : Build de l'application
FROM maven:3.8.5-openjdk-17 AS build
WORKDIR /app

# Copier uniquement les fichiers nécessaires en priorité pour le cache Docker
COPY pom.xml .
COPY src ./src

# Résolution des dépendances et compilation (on skip les tests)
RUN mvn clean package -DskipTests

# Étape 2 : Image d'exécution
FROM openjdk:17
WORKDIR /app
COPY --from=build /app/target/*.jar app.jar

EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
