
# SkillSprint — Product Brief

## 1. Product Overview

SkillSprint — онлайн-платформа для профессионального обучения в формате cohort-based courses.

Первые направления:

- UX/UI Design
- Product Management
- Digital Marketing
- Data Analytics
- AI Tools for Work

В дальнейшем платформа сможет расширяться на другие business и tech-направления.

У SkillSprint уже существуют:

- branding;
- marketing website;
- первые образовательные программы находятся в подготовке.

Текущая задача — спроектировать **student learning platform**, которую development team сможет реализовать как первую версию продукта.

Ориентировочный срок запуска MVP — 3 месяца.

---

# 2. Product Goal

Главная задача продукта — помочь студенту пройти профессиональный курс от начала до конца без необходимости самостоятельно разбираться:

- что делать дальше;
- какие материалы изучать;
- какие задания выполнять;
- какие дедлайны приближаются;
- когда проходят live sessions;
- какой feedback получен от mentor;
- насколько студент продвинулся по программе.

Основной UX-принцип:

> В любой момент пользователь должен понимать, где он находится в курсе и какое действие ему следует выполнить следующим.

Платформа должна ощущаться как организованная learning environment, а не как библиотека видео.

---

# 3. MVP Product Principles

Для первой версии продукта приоритет:

1. Простота.
2. Понятная структура обучения.
3. Минимальное количество действий для студента.
4. Чёткое отображение текущего состояния.
5. Поддержка cohort-based learning.
6. Assignments и mentor feedback являются важной частью курса.
7. Desktop-first responsive web application.
8. Не перегружать MVP дополнительными marketplace, social и gamification-функциями.

---

# 4. Primary Users

## Student

Основной пользователь платформы.

Это взрослые специалисты или люди, развивающие профессиональные навыки.

Предполагаемый уровень:

- beginner;
- junior;
- middle professional;
- career switcher.

Типичный студент:

- работает или учится параллельно;
- может уделять обучению несколько часов в неделю;
- ожидает практический результат;
- хочет понимать свой прогресс;
- ценит структуру и поддержку mentor.

---

## Mentor

Помогает студентам:

- выполнять assignments;
- получать feedback;
- разбираться с вопросами;
- двигаться по программе.

В MVP mentor может работать сразу с группой студентов одного cohort.

---

## Instructor

Человек, ведущий курс или live sessions.

В первой версии роли Mentor и Instructor могут частично пересекаться.

---

## Admin

Управляет:

- courses;
- cohorts;
- lessons;
- students;
- mentors;
- assignments;
- schedule;
- announcements.

Полноценный сложный admin product не является основным предметом student UX-проекта.

---

# 5. Core Product Structure

Основная информационная модель:

Course  
→ Cohort  
→ Module  
→ Lesson  
→ Assignment

Дополнительные сущности:

- Live Session
- Resource
- Mentor
- Student
- Feedback
- Announcement

---

# 6. Course

Course — образовательная программа определённого направления.

Пример:

**UX/UI Design**

Course содержит:

- description;
- learning outcomes;
- modules;
- lessons;
- assignments;
- resources;
- instructors;
- mentors.

Один Course может запускаться несколько раз через разные Cohorts.

---

# 7. Cohort

Cohort — конкретная группа студентов, проходящая Course в определённый период времени.

Cohort имеет:

- start date;
- end date;
- students;
- mentors;
- schedule;
- live sessions;
- deadlines.

Все участники одного cohort проходят программу примерно в одном темпе.

Для MVP предполагается, что программа имеет определённую последовательность и ориентировочный учебный график.

---

# 8. Course Progression

Основная модель обучения:

Module 1  
↓  
Lessons  
↓  
Assignment  
↓  
Module 2  
↓  
Lessons  
↓  
Assignment  
↓  
…  
↓  
Final Project  
↓  
Course Completion

Материалы могут быть доступны заранее либо постепенно открываться по расписанию.

Для MVP предпочтительный вариант:

**modules открываются последовательно по расписанию cohort, но просмотр доступного контента не блокируется строгими prerequisites.**

Это упрощает разработку и снижает количество edge cases.

---

# 9. Modules

Course состоит из нескольких Modules.

Каждый Module соответствует определённой теме или learning outcome.

Module содержит:

- title;
- short description;
- lessons;
- resources;
- assignment;
- estimated duration;
- module progress.

Пример:

Module 01 — UX Research  
Module 02 — User Flows  
Module 03 — Wireframing  
Module 04 — Prototyping  
Module 05 — User Testing  
Module 06 — Final Project

---

# 10. Lessons

Lesson — основной образовательный элемент.

В MVP поддерживаются:

- video lesson;
- text content;
- downloadable resources;
- links.

Каждый lesson может иметь:

- title;
- description;
- estimated duration;
- video;
- supporting text;
- resources;
- completion state.

Основные состояния:

- Not started
- In progress
- Completed

Пользователь может самостоятельно отметить lesson как completed.

Для видео желательно сохранять последний просмотренный момент, если техническая реализация позволяет это сделать без существенного увеличения scope.

---

# 11. Assignments

Assignments — практическая часть обучения.

Студент должен иметь возможность:

- открыть описание задания;
- изучить requirements;
- увидеть deadline;
- добавить ответ;
- загрузить файл;
- добавить ссылку;
- submit assignment;
- получить mentor feedback.

Поддерживаемые форматы submission для MVP:

- text;
- link;
- file attachment.

Это покрывает большинство задач UX/UI, Product, Marketing, Analytics и AI courses.

---

# 12. Assignment States

Базовая логика:

Not Started  
→ In Progress  
→ Submitted  
→ Reviewed  
→ Completed

Если mentor просит изменить работу:

Submitted  
→ Reviewed  
→ Needs Revision  
→ Resubmitted  
→ Completed

Оценки в формате numerical grades для MVP не нужны.

Основной тип оценки:

**qualitative mentor feedback.**

---

# 13. Deadlines

Assignment может иметь due date.

До deadline студент видит стандартное состояние.

После deadline assignment становится:

**Overdue**

но остаётся доступным для submission.

Строго блокировать дальнейшее обучение из-за просроченного assignment не нужно.

---

# 14. Mentor Experience

Каждый cohort имеет одного или нескольких mentors.

Студент может:

- видеть своего mentor;
- получать feedback на assignments;
- видеть статус review;
- обращаться с вопросами через предусмотренный communication channel.

Для MVP не требуется полноценная встроенная messenger system.

Предпочтительный вариант:

### Assignment Feedback

Комментарии mentor внутри assignment.

### General Questions

Внешний communication tool либо простой discussion mechanism.

Это позволяет избежать разработки сложного real-time chat.

---

# 15. Live Learning

SkillSprint поддерживает live sessions.

Типы:

- Live Class
- Workshop
- Q&A
- Office Hours
- Project Review

Live sessions могут проходить через внешние сервисы:

- Zoom;
- Google Meet;
- аналогичный video provider.

Платформа показывает:

- title;
- date;
- time;
- duration;
- instructor;
- meeting link.

После завершения session может появляться запись.

---

# 16. Schedule

Студент должен видеть расписание курса.

Schedule включает:

- live sessions;
- assignment deadlines;
- important cohort events.

Для MVP достаточно одного общего course schedule.

Calendar integration является полезной дополнительной функцией, но не критичной для основной логики продукта.

---

# 17. Student Dashboard

Dashboard является главным entry point после входа в систему.

Его задача — ответить на четыре вопроса:

1. Где я сейчас?
2. Что мне делать дальше?
3. Что скоро произойдёт?
4. Насколько я продвинулся?

Dashboard агрегирует информацию из разных частей продукта.

Основные категории информации:

### Current Learning

Текущий module и следующий рекомендуемый action.

### Progress

Общий progress курса.

### Upcoming

Ближайшие:

- live session;
- assignment deadline;
- important event.

### Assignments

Задания, которые требуют внимания.

### Mentor Feedback

Новый или непрочитанный feedback.

### Course Updates

Важные announcements.

---

# 18. Next Action Logic

Платформа должна определять наиболее логичное следующее действие студента.

Пример приоритета:

1. Overdue assignment
2. Assignment requiring revision
3. Assignment approaching deadline
4. Upcoming live session
5. Continue current lesson
6. Start next lesson
7. Start next module

Для MVP не требуется сложная AI-система рекомендаций.

Это обычная deterministic product logic.

---

# 19. Progress

В MVP progress рассчитывается достаточно просто.

Course Progress основан преимущественно на:

- completed lessons;
- completed assignments.

Live session attendance не является обязательной частью progress.

Пример:

60% lessons completed  
+  
40% assignments completed

могут формировать общий weighted progress.

Точная математическая формула является implementation detail и может быть определена позже.

Главное — progress должен отражать реальное продвижение по course structure.

---

# 20. Learning Outcomes

Каждый Course должен иметь набор learning outcomes.

Modules желательно связывать с конкретными результатами.

Например:

UX/UI Course:

- Conduct user research
- Build user flows
- Create wireframes
- Design prototypes
- Perform usability testing

В MVP отдельная сложная Skills Management System не требуется.

Learning outcomes используются прежде всего для организации содержания курса.

---

# 21. Course Completion

Course считается завершённым, когда:

- обязательные lessons пройдены;
- обязательные assignments выполнены;
- final assignment/project submitted.

После завершения студент получает Completed status.

Certificate может быть добавлен как простая функция, если это требуется бизнесу.

Сложную credential system создавать не нужно.

---

# 22. Portfolio

Поскольку SkillSprint специализируется на практических professional courses, выполненные assignments могут в дальнейшем стать основой student portfolio.

Однако полноценный portfolio builder не является частью MVP.

Важно только структурировать assignments таким образом, чтобы эту функцию можно было добавить позже.

---

# 23. Community

Community является частью cohort-based experience, но полноценную social network строить не нужно.

Для MVP достаточно лёгкого уровня взаимодействия.

Возможные возможности:

- cohort announcements;
- discussions;
- comments;
- peer project viewing.

Private messaging, followers, feeds и сложные social mechanics не требуются.

---

# 24. Student Profiles

Каждый student имеет простой profile.

Основные данные:

- name;
- avatar;
- current role;
- company — optional;
- location — optional;
- short bio;
- LinkedIn — optional.

Профиль помогает участникам cohort понимать, с кем они учатся.

---

# 25. Onboarding

После первого входа студент проходит короткий onboarding.

Цель — не собирать большое количество информации, а подготовить пользователя к обучению.

Возможные шаги:

1. Welcome
2. Basic profile
3. Learning goal
4. Overview of course structure
5. Start learning

Можно добавить onboarding checklist.

Например:

- Complete profile
- Explore course
- Check schedule
- Start first lesson

---

# 26. Multiple Courses

Архитектура должна поддерживать возможность одного пользователя иметь несколько courses.

Но для MVP основной сценарий:

**один пользователь активно проходит один основной course.**

Продукт должен предусматривать:

- Active Courses
- Completed Courses

Если пользователь имеет несколько courses, появляется My Learning.

---

# 27. Course Discovery

Marketing website уже существует.

Поэтому полноценный Course Marketplace внутри learning platform для MVP не нужен.

Покупка и discovery происходят преимущественно на marketing website.

После покупки пользователь получает доступ к course через student platform.

В дальнейшем внутри продукта может появиться:

- Browse Courses
- Recommended Courses
- Enroll in another program

но это Phase 2.

---

# 28. Main Product Navigation

Основные product areas:

### Home

Главный student dashboard.

### Learn

Course structure, modules и lessons.

### Assignments

Assignments и feedback.

### Schedule

Live sessions и deadlines.

### Community

Cohort interaction.

### Profile

Student account и profile.

Количество основных разделов следует сохранять минимальным.

---

# 29. Notifications

Основные события:

- assignment deadline approaching;
- assignment overdue;
- mentor feedback received;
- assignment requires revision;
- live session upcoming;
- new module available;
- important announcement.

Channels:

### MVP

- in-app;
- email.

Push notifications не нужны, пока нет native mobile application.

---

# 30. Announcements

Instructor/Admin может публиковать сообщения для cohort.

Примеры:

- schedule change;
- new resource;
- session update;
- important reminder.

Announcement является one-to-many communication и не требует сложной messaging architecture.

---

# 31. Search

Global search не является необходимым элементом MVP.

Если понадобится, search можно добавить позже для:

- lessons;
- resources;
- courses.

---

# 32. Resources

Resources могут быть связаны:

- с конкретным lesson;
- с module;
- со всем course.

Форматы:

- PDF;
- template;
- checklist;
- link;
- document;
- downloadable file.

Не обязательно создавать отдельную сложную Resource Library в MVP.

---

# 33. Mobile

Продукт создаётся как responsive web application.

Основной use case — desktop/laptop.

Mobile должен позволять:

- посмотреть dashboard;
- посмотреть lesson;
- посмотреть schedule;
- читать feedback;
- выполнять простые действия.

Сложные assignments предполагается чаще выполнять на desktop.

Native application не является частью MVP.

---

# 34. Integrations

Вероятные integrations:

### Video hosting
Vimeo / YouTube / аналог.

### Live sessions
Zoom / Google Meet.

### Payments
Остаются частью marketing/enrollment infrastructure.

### File storage
Cloud storage.

### Email
Transactional email provider.

Интеграции должны использовать существующие сервисы вместо разработки собственных аналогов.

---

# 35. Admin Logic

Admin должен иметь возможность управлять базовыми сущностями:

- create/edit Course;
- create Cohort;
- add Modules;
- add Lessons;
- add Assignments;
- upload Resources;
- define deadlines;
- schedule Live Sessions;
- assign Mentors;
- manage Students;
- publish Announcements.

Admin interface может быть значительно более утилитарным, чем student-facing product.

Если timeline ограничен, полноценный custom admin dashboard можно заменить существующим CMS/backend solution.

---

# 36. Core Student Journey

Основной happy path:

Marketing Website  
→ Enroll  
→ Account Created  
→ First Login  
→ Onboarding  
→ Student Dashboard  
→ Start Module  
→ Watch Lesson  
→ Complete Lesson  
→ Continue Lessons  
→ Open Assignment  
→ Submit Assignment  
→ Mentor Reviews  
→ Receive Feedback  
→ Complete / Revise Assignment  
→ Continue Course  
→ Join Live Sessions  
→ Complete Final Project  
→ Course Completed

Это основной flow, вокруг которого проектируется MVP.

---

# 37. Mentor Journey

Mentor:

Login  
→ View Cohort  
→ View Students / Assignments  
→ Open Submission  
→ Review Work  
→ Leave Feedback  
→ Mark Completed / Request Revision  
→ Continue to Next Submission

Mentor analytics и сложный performance dashboard в MVP не требуются.

---

# 38. Important States

Продукт должен предусматривать следующие состояния.

### Course

- Upcoming
- Active
- Completed

### Module

- Locked / Upcoming
- Available
- In Progress
- Completed

### Lesson

- Not Started
- In Progress
- Completed

### Assignment

- Not Started
- In Progress
- Submitted
- Under Review
- Needs Revision
- Completed
- Overdue

### Feedback

- New
- Read

### Live Session

- Upcoming
- Live
- Completed
- Recording Available

---

# 39. Empty States

Нужно предусмотреть ситуации:

- no assignments;
- no upcoming events;
- no feedback;
- no announcements;
- course not started yet;
- all tasks completed;
- no additional courses.

Empty state должен объяснять текущую ситуацию и, когда возможно, предлагать следующее действие.

---

# 40. Error / Edge Cases

Для MVP достаточно предусмотреть основные ситуации:

- failed file upload;
- unavailable video;
- expired meeting link;
- assignment submitted after deadline;
- mentor has not reviewed submission yet;
- course content unavailable;
- user has no active course.

Сложные exception flows можно определить позже.

---

# 41. Accessibility

Продукт должен использовать базовые WCAG-compatible practices:

- readable typography;
- sufficient contrast;
- keyboard accessibility;
- clear focus states;
- captions/transcripts для видео при возможности;
- интерфейс не должен передавать критичную информацию только цветом.

---

# 42. Success Metrics

Главные product metrics:

### Activation

Student starts first lesson.

### Engagement

Student returns to platform and continues learning.

### Learning Progress

Percentage of lessons and assignments completed.

### Assignment Completion

Students successfully submit practical work.

### Course Completion

Percentage of students completing the program.

### Cohort Engagement

Participation in live sessions / discussions.

### Mentor Interaction

Assignments receiving feedback.

Для MVP не требуется сложная analytics dashboard, но события желательно предусмотреть при разработке.

---

# 43. Product Differentiation

SkillSprint не должен конкурировать только количеством контента.

Основное позиционирование продукта:

> Practical professional learning that keeps students moving toward a concrete outcome.

Ключевые differentiators:

### 1. Action-Oriented Learning

Платформа всегда помогает понять следующий шаг.

### 2. Practical Assignments

Learning строится не только вокруг просмотра контента, но вокруг работы.

### 3. Mentor Support

Feedback является частью основного learning journey.

### 4. Cohort Experience

Студент чувствует, что учится вместе с другими людьми.

### 5. Outcome-Oriented Progress

Главный показатель — движение к профессиональному результату, а не просто количество просмотренных видео.

---

# 44. Potential Phase 2 Features

Эти возможности важно предусмотреть концептуально, но не включать в основной MVP scope.

### Skills Profile

Отображение развиваемых профессиональных навыков.

### Student Portfolio

Сохранение лучших assignments как portfolio projects.

### AI Learning Assistant

AI, знающий материалы курса и помогающий:

- объяснять темы;
- отвечать на вопросы;
- проводить quizzes;
- помогать работать над assignments.

### Personalized Learning Recommendations

Персональные рекомендации следующего шага.

### Advanced Community

- peer reviews;
- DMs;
- student groups;
- networking.

### Gamification

- badges;
- streaks;
- achievements.

### Course Marketplace

Discovery и enrollment непосредственно внутри platform.

### Certificates / Credentials

Расширенная система certificates.

### Mentor Booking

1:1 sessions и calendar booking.

---

# 45. Explicitly Out of Scope for MVP

Чтобы уложиться в трёхмесячный запуск, в первую версию не следует включать:

- native mobile apps;
- custom video conferencing;
- complex messaging;
- full social network;
- advanced gamification;
- sophisticated AI assistant;
- recommendation algorithms;
- full portfolio builder;
- advanced skills assessment;
- internal marketplace;
- complex payment system;
- advanced analytics;
- elaborate admin system;
- peer grading system;
- custom calendar infrastructure.

---

# 46. Recommended MVP Scope

Минимальная полноценная версия SkillSprint включает:

## Student

- Authentication
- Onboarding
- Home Dashboard
- Course
- Modules
- Lessons
- Video Content
- Resources
- Lesson Completion
- Assignments
- Submission
- Deadlines
- Mentor Feedback
- Course Progress
- Live Session Schedule
- Announcements
- Basic Community
- Profile

## Mentor

- Cohort overview
- Student submissions
- Assignment review
- Feedback
- Request revision / complete assignment

## Admin

- Course management
- Cohort management
- Content management
- Assignment management
- Mentor assignment
- Schedule management
- Announcement management

---

# 47. UX Priority

При принятии UX-решений используется следующий порядок приоритетов:

1. Student understands what to do next.
2. Student understands course structure.
3. Student sees important deadlines/events.
4. Student can consume learning content.
5. Student can complete practical assignments.
6. Student can receive mentor feedback.
7. Student understands progress.
8. Student can interact with cohort.
9. Secondary functionality.

---

# 48. Product Tone

Продукт должен восприниматься как:

- professional;
- modern;
- focused;
- supportive;
- structured;
- motivating without being childish.

Он не должен ощущаться как школьная LMS или gamified children's learning platform.

Основная аудитория — взрослые professionals.

---

# 49. Core Product Statement

**SkillSprint helps professionals move through structured, practical cohort-based courses by always making the next step clear and connecting learning content with assignments, deadlines, mentors and measurable progress.**

---

# 50. Design Task

На основе этого brief необходимо разработать UX/UI student learning platform SkillSprint.

Основная задача дизайна — определить:

- information architecture;
- navigation;
- hierarchy;
- user flows;
- relationship between course content, assignments, schedule and mentor feedback;
- states;
- responsive behaviour.

Необходимо сначала разработать core experience:

**Dashboard → Course → Lesson → Assignment → Submission → Mentor Feedback → Continue Learning**

и только после этого расширять остальные sections.

Финальный интерфейс должен быть достаточно простым для MVP, но информационная архитектура должна позволять продукту в будущем расширяться до multi-course professional learning ecosystem.