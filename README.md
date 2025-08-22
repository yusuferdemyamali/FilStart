
# FilStart: AI-Powered Laravel & Filament Starter Project

![FilStart Banner](https://placehold.co/1200x400/0D1117/FFFFFF/png?text=FilStart)

## ✨ About The Project

**FilStart** is a comprehensive, feature-rich starter project built on **Laravel 12** and **Filament 3**. It's designed to be more than just a template; it's a powerful foundation for building modern, scalable, and secure web applications with unprecedented speed. FilStart integrates AI-powered development automation, pre-configured performance optimizations, and robust security best practices right out of the box.

This project was born from the need to accelerate the initial setup and development phases of a project, allowing developers to focus on building unique features instead of repetitive boilerplate code. By leveraging a sophisticated system of prompts and context-aware scripts, FilStart automates common development tasks, from code generation to quality audits.

### Key Features

*   **Solid Foundation**: Built on the latest versions of Laravel and Filament, providing a modern, stable, and elegant starting point.
*   **AI-Powered Automation**: A unique system using `prompts` and `commands` to automate development workflows, including task breakdown, code generation, and quality analysis.
*   **Performance First**: Comes with pre-configured settings and a detailed `PERFORMANCE_OPTIMIZATION_SUMMARY.md` to ensure your application is fast and scalable from day one.
*   **Security by Default**: Includes a `PRODUCTION_CHECKLIST.md` and `security_best_practices_laravel.md` to guide you in building a secure application.
*   **Ready-to-Deploy**: Contains sample deployment scripts for both Windows (`deploy.bat`) and Linux (`deploy.sh`) environments.
*   **Rich Context**: A dedicated `context` directory to store all project-related documentation, from client requirements to technical specifications, ensuring all stakeholders are aligned.
*   **Complete Tooling**: Pre-configured with Vite, Pest for testing, and a standard project structure that is both intuitive and scalable.

## 🚀 Getting Started

Follow these steps to get your local development environment up and running.

### Prerequisites

*   PHP >= 8.2
*   Laravel 12
*   Filament 3.X
*   Composer
*   A database (e.g., MySQL, PostgreSQL, SQLite)

### Installation

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/yusuferdemyamali/starter_project.git filstart
    cd filstart
    ```

2.  **Install PHP dependencies:**
    ```sh
    composer install
    ```

3.  **Create your environment file:**
    ```sh
    cp .env.example .env
    ```

4.  **Generate an application key:**
    ```sh
    php artisan key:generate
    ```

5.  **Configure your database:**
    Open the `.env` file and set your database credentials (`DB_DATABASE`, `DB_USERNAME`, `DB_PASSWORD`, etc.).

6.  **Run database migrations and seeders:**
    ```sh
    php artisan migrate --seed
    ```

7.  **Build frontend assets:**
    ```sh
    npm run dev
    ```
    *(For production, use `npm run build`)*

8.  **Serve the application:**
    ```sh
    php artisan serve
    ```

You can now access your application at `http://127.0.0.1:8000` and the Filament admin panel at `http://127.0.0.1:8000/admin`.

## 🛠️ Development & Usage

### AI-Powered Workflow

The core of FilStart's automation lies in the `prompts` and `commands` directories.

*   **`prompts/`**: Contains templates for generating code, reports, and task lists. These are designed to be used with large language models (LLMs) to streamline development.
*   **`commands/`**: Contains text files that describe step-by-step processes for complex tasks like `code_quality_audit.txt` or `performance_security_report.txt`.

This system allows you to maintain a consistent and high-quality development process by codifying best practices into executable and repeatable steps.

### Project Context

The `context/` directory is crucial for keeping your project well-documented and aligned with its goals. It includes:
*   `project_brief.md`
*   `client_requirements.md`
*   `technical_specifications.md`
*   `database_schema.md`
*   And more...

Keeping this information centralized and up-to-date is key to the success of the AI-powered automation features.

### Testing

This project uses **Pest** for testing. To run the test suite, execute the following command:

```sh
php artisan test
```

## 📁 Project Structure

The project follows a standard Laravel structure with some additions to support its unique features:

```
/app                    - Core application code (Models, Controllers, Filament Resources)
/bootstrap              - Application bootstrapping scripts
/commands               - AI-driven command descriptions
/config                 - Application configuration files
/context                - Project documentation and specifications
/database               - Migrations, factories, and seeders
/output                 - Generated reports and artifacts
/prompts                - Templates for AI-powered code/text generation
/public                 - Web server's document root
/resources              - Frontend assets (CSS, JS, Views)
/routes                 - Route definitions (web, api)
/storage                - Compiled assets, logs, and file storage
/tests                  - Application tests (Unit, Feature)
/vendor                 - Composer dependencies
```

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

## 📜 License

Distributed under the MIT License. See `LICENSE` file for more information. (Note: A `LICENSE` file should be added to the repository).

## 📧 Contact

Yusuf Erdem Yamalı - yusufyamali.me - yusuferdem.dev@gmail.com


