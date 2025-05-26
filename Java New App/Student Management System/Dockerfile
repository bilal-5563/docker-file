# ===== Stage 1: Build =====

FROM eclipse-temurin:18-jdk AS builder


WORKDIR /app/student-management

COPY . /app

RUN javac App.java packages/fileHandler/*.java packages/system/*.java

# ===== Stage 2: Runtime =====

FROM eclipse-temurin:18-jre-alpine

WORKDIR /app

COPY --from=builder /app/student-management  /app

CMD ["java","App"]
