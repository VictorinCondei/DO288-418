#FROM registry.ocp4.example.com:8443/redhattraining/ocpdev-ubi8-openjdk-17-base:1.16
FROM default-route-openshift-image-registry.apps.rm1.0a51.p1.openshiftapps.com/openshift/ubi8-openjdk-17:1.16

COPY pom.xml .
RUN mvn dependency:go-offline

COPY src src
RUN mvn clean package

CMD ["java", "-jar", "target/expense-service-1.0.0-SNAPSHOT-runner.jar"]
