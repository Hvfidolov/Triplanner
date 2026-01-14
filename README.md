# Triplanner
### Co=Pilot prompt for clean architecture :
This Flutter project is a Clean Architecture SaaS app for a World Cup 2030 Morocco travel platform.

We strictly follow 3 layers per feature:

Domain (business rules, entities, use cases, repository interfaces – no Flutter imports)
Data (API, Firebase, local DB, ML model adapters – implements domain repositories)
Presentation (UI + Cubit/BLoC – no API calls, no JSON, no data models)

UI widgets communicate ONLY with Cubit/BLoC.
Cubit communicates ONLY with UseCases.
UseCases communicate ONLY with Repository interfaces.
Repositories are implemented in the Data layer using remote, local, or ML data sources.

All UI components (buttons, cards, inputs, trip tiles, food cards, etc.) must be reusable widgets stored in core/widgets/.

Features are isolated by folders:
features/trips, features/food, features/sights, features/auth, features/recommendation, etc.

The future recommendation system (ML model) must be accessed only through a RecommendationRepository in the Domain layer, never directly from UI or Cubit.

No Widget may contain business logic, API calls, model inference, or data parsing.
