# PlantUML Code
---

## Domain Classes
<!-- 
https://www.plantuml.com/plantuml/uml/SoWkIImgAStDuKhDAyaigLHm1LC6XWhLN0eAMWgPAI3njChClFJun9AIeioaqf9Ke8okBbWwDp4l9R4alwWIHJA_e2GpFoyn1qcmbiiXDIy5P0y0
-->
```
@startuml
title Domain class diagram
header Class Planner

entity School {
}

rectangle " " as school {
 entity User {
 }

 entity Director {
 }

 entity Coordinator {
 }

 entity Professor {
 }

 entity Subject {
 }

 entity Classroom {
 }

 entity "Lesson" as Class {
 }

 Class o-- Subject
 Class o-- Professor
 Class o-- Classroom
 Classroom -- Professor
 Subject -- Professor
 Professor --|> User
 Director --|> User
 Coordinator --|> User
}

School <-right- school

@enduml
```

## Lesson Usecases
<!-- 
https://www.plantuml.com/plantuml/uml/SoWkIImgAStDuIhEpimhI2nAp5L8J2x9BmekgSn9LKWiJotEpqtbiWejJYsoKj3LjLFG038rkPHy4pFp51nJSZFpb1GIYo4iBYMWd4991b1VGK5EPd9YIMO-H1gY2Qm8OWY4YQPKayiXDIy5v1W0
-->
```
@startuml
title Usecase diagram
header Class Planner
skinparam actorStyle awesome
left to right direction

:Professor:

rectangle Lesson {
 (Create new Lesson)
 (Update Lesson)
 (List my Lessons)
 (Filter Lessons by Professor)
 (Filter Lessons by Subject)
 (Filter Lessons by Classroom)
}

Professor -- (Create new Lesson)
Professor -- (Update Lesson)
Professor -- (List my Lessons)
Professor -- (Filter Lessons by Professor)
Professor -- (Filter Lessons by Subject)
Professor -- (Filter Lessons by Classroom)
@enduml
```

## Subject usecase
```
@startuml
title Usecase diagram
header Class Planner
skinparam actorStyle awesome
left to right direction

rectangle Subject {
 (Create new Subject) as create
 (Update Subject) as update
 (Disable Subject) as disable
 (Enable Subject) as enable
 (List Subjects) as list
}

:Coordinator:
:Professor:

Coordinator -> Professor
Professor -- create
Professor -- update
Professor -- disable
Professor -- enable
Professor -- list

@enduml
```