File architecture for the project (concise)

Root
├─ build.xml                 # Ant build file
├─ manifest.mf
├─ library_management.sql    # DB schema + seed data
├─ lib/                      # third-party jars and docs
│  ├─ JTattoo-1.6.11.jar
│  ├─ rs2xml.jar
│  └─ MySQLDriver/
│     └─ mysql-connector-java-5.1.23-bin.jar
├─ src/
│  ├─ DAO/
│  │  └─ DatabaseHelper.java
│  ├─ images/                 # app images used by UI
│  │  ├─ book.png
│  │  ├─ add.png
│  │  └─ ...
│  └─ Library_Management/     # main application package
│     ├─ Home.java
│     ├─ Login.java
│     ├─ Signup.java
│     ├─ NewBook.java
│     ├─ Issue.java
│     ├─ Return.java
│     ├─ Statistics.java
│     ├─ Student.java
│     ├─ Forgot.java
│     └─ *.form                # NetBeans GUI form metadata
├─ build/                     # compiled classes and build artifacts
│  └─ classes/
│     ├─ Library_Management/*.class
│     └─ DAO/DatabaseHelper.class
├─ nbproject/                 # NetBeans project metadata
└─ test/

How to view the PlantUML diagram
1) If you use VS Code, install the "PlantUML" extension and open `docs/architecture.puml`.
2) Or render with the PlantUML jar (requires Java):

```powershell
# from project root (Windows PowerShell)
java -jar C:\path\to\plantuml.jar docs\architecture.puml
# this produces docs/architecture.png
```

Notes and mapping
- Source code lives under `src/` - split between `DAO` (data access) and `Library_Management` (UI/controllers).
- `lib/` contains external libraries (UI look-and-feel, database driver, rs2xml for JTable->ResultSet).
- `build/` contains compiled `.class` files produced by Ant; `java -cp "build/classes;lib/*" Library_Management.Home` runs the app.

If you'd like, I can also:
- Generate a PNG from the PlantUML file and add it to `docs/` (I can render it locally if you want), or
- Produce a more detailed UML class diagram listing concrete classes and their relationships.

---
Generated on: Oct 6, 2025
