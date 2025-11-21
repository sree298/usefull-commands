# ☕ Maven Commands Cheat Sheet

## 🔍 Maven Version & Help
| Command | Description |
|--------|-------------|
| `mvn -version` | Check Maven version |
| `mvn -v` | Show version details |
| `mvn -h` | Maven help |

---

## 🛠 Build & Package Commands
| Command | Description |
|--------|-------------|
| `mvn clean` | Remove previous build files |
| `mvn compile` | Compile source code |
| `mvn package` | Create a JAR/WAR package |
| `mvn install` | Build and install into local repository |
| `mvn test` | Run unit tests |
| `mvn clean install` | Clean + compile + test + package |
| `mvn clean package` | Clean + package project |

---

## 🚀 Running Applications
| Command | Description |
|--------|-------------|
| `mvn spring-boot:run` | Run Spring Boot application |
| `mvn exec:java` | Run Java application |
| `mvn jetty:run` | Run web project using Jetty server |

---

## 📦 Dependency & Repository Commands
| Command | Description |
|--------|-------------|
| `mvn dependency:tree` | Show dependency tree |
| `mvn dependency:resolve` | Resolve dependencies |
| `mvn dependency:list` | List dependencies |

---

## 🔧 Maven Lifecycle Phases
| Phase | Purpose |
|-------|---------|
| `validate` | Validate project configuration |
| `compile` | Compile the source |
| `test` | Run tests |
| `package` | Package into JAR/WAR |
| `verify` | Check integration tests |
| `install` | Install to local repo |
| `deploy` | Deploy to remote repo |

---

## 🧹 Cleaning & Troubleshooting
| Command | Description |
|--------|-------------|
| `mvn clean` | Remove target directory |
| `mvn -U clean install` | Force update snapshot dependencies |
| `mvn help:effective-pom` | Show final effective POM |

---

## 🎯 Skip Tests
| Command | Description |
|--------|-------------|
| `mvn install -DskipTests` | Skip test execution |
| `mvn clean package -DskipTests` | Build without running tests |

---

## 📝 Example Full Build Command
```bash
mvn clean install -DskipTests
