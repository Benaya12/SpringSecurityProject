Spring Security Demo – Role-Based Access Control
תיאור הפרויקט

פרויקט Spring Boot לדוגמה שמיישם ניהול תפקידים (RBAC) באמצעות Spring Security.
כולל:

Authentication עם שם משתמש וסיסמה.

Authorization מבוסס תפקידים (ADMIN, USER, MANAGER).

נתיבים ציבוריים, למשתמשים ולמנהלים.

טעינת משתמשים ותפקידים ראשוניים בעת אתחול.

דרישות

Java 17+

Maven או Gradle

מסד נתונים (H2 מובנה או MySQL/PostgreSQL)

מבנה הפרויקט
src/main/java/org/example/springsecuritydemo/
│
├── Config/
│   ├── SecurityConfig.java
│   ├── RoleInitializer.java
│   └── UserInitializer.java
│
├── Controller/
│   ├── PublicController.java
│   ├── UserController.java
│   └── AdminController.java
│
├── Entity/
│   ├── User.java
│   └── Role.java
│
├── Model/
│   └── CustomUserDetails.java
│
├── Repository/
│   ├── UserRepository.java
│   └── RoleRepository.java
│
└── Service/
    └── AuthApiUserDetailsService.java

התקנה והרצה
1. בניית הפרויקט
mvn clean install


או אם אתה משתמש ב־Gradle:

./gradlew build

2. הרצת האפליקציה
mvn spring-boot:run


או עם Gradle:

./gradlew bootRun


האפליקציה תרוץ ב־http://localhost:8080.

משתמשים ותפקידים ראשוניים
משתמש	סיסמה	תפקיד
roei	roei	ROLE_ADMIN
yossi	yossi	ROLE_USER

ניתן להוסיף משתמשים נוספים דרך מחלקת UserInitializer או דרך מסד הנתונים.
