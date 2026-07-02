# WebDev-Fullstack

This repository documents my journey of learning backend development more deeply using Laravel. I created it to prepare for my upcoming semester, improve my backend development skills, and support my role as a Backend Club mentor.

Figma design: https://www.figma.com/design/RIkwN6PsVM20OPHDzAFQ4t/Design-Figma-Web-Pinjam-Ruang-Gedung?node-id=0-1&t=9Sr6dSh94s0TrlIy-1
Words bangun rancang: https://docs.google.com/document/d/1b4LQ8aj9m5qNnGqQb0zbVhD1QX7JlkKz556OgPxAlNk/edit?usp=sharing
---

# Laravel Project Setup Guide

This guide covers two scenarios:

1. **Creating a new Laravel project from scratch.**
2. **Cloning this repository and running it locally.**

---

## Prerequisites

Make sure you have installed:

* PHP >= 8.2
* Composer
* Node.js & NPM
* MySQL
* Git

---

# A. Initial Laravel Project Setup (For New Project)

> **Note**
>
> If you are creating a brand-new Laravel project, it is recommended to **create the Laravel application first before initializing Git or connecting it to a GitHub repository**.
>
> This is because `composer create-project` expects an **empty directory**. If the directory already contains files (such as `README.md`, `.gitignore`, or an existing Git repository), Composer may display:
>
> ```
> Project directory ".../" is not empty.
> ```
>
> Once Laravel has been created successfully, you can initialize Git and push the project to GitHub.

### 1. Create a New Laravel Project

If you are already inside an empty directory, run:

```bash
composer create-project laravel/laravel .
```

Or, if you prefer Composer to create a new project folder for you:

```bash
composer create-project laravel/laravel your-project-name
cd your-project-name
```

> **Note**
>
> `composer create-project laravel/laravel .`
>
> * Installs Laravel into the **current directory**.
> * Composer **does not create a new folder**.
> * The current directory **must be empty**.
>
> `composer create-project laravel/laravel your-project-name`
>
> * Composer creates a **new directory** named `your-project-name`.
> * Laravel will be installed inside that directory.
> * This is the recommended option when starting a completely new Laravel project.

### 2. (Optional) Initialize Git

After Laravel has been created successfully, initialize Git and connect it to your GitHub repository.

```bash
git init
git add .
git commit -m "Initial Laravel project"
git branch -M main
git remote add origin https://github.com/your-username/your-repository.git
git push -u origin main
```

### 3. Install PHP Dependencies

> **Note**
>
> If you created the project using `composer create-project`, Composer has **already installed all PHP dependencies automatically**, so you may skip this step.
>
> However, if you are contributing to an existing project, restoring a deleted `vendor` directory, or need to reinstall the dependencies, run:

```bash
composer install
```

### 4. Install Frontend Dependencies

```bash
npm install
```

### 5. Configure Environment

Laravel automatically provides a `.env` file.

Update your database configuration:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=your_database
DB_USERNAME=your_username
DB_PASSWORD=your_password
```

### 6. Generate Application Key

```bash
php artisan key:generate
```

### 7. Run Database Migration

```bash
php artisan migrate
```

### 8. Start Development Server

**Option 1 (Recommended for Linux/macOS):**

```bash
composer run dev
```

**Option 2 (Recommended for Windows):**

Open two terminals.

**Terminal 1**

```bash
php artisan serve
```

**Terminal 2**

```bash
npm run dev
```

Open:

```
http://localhost:8000
```

---

# B. Clone & Setup This Repository

If you already cloned this repository, follow these steps.

## 1. Clone Repository

```bash
git clone https://github.com/KrishnaArdiDev/WebDev-Fullstack.git
cd WebDev-Fullstack
```

## 2. Install PHP Dependencies

```bash
composer install
```

## 3. Install JavaScript Dependencies

```bash
npm install
```

## 4. Setup Environment File

```bash
cp .env.example .env
```

After copying the `.env` file, configure your database:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=your_database
DB_USERNAME=your_username
DB_PASSWORD=your_password
```

## 5. Generate Application Key

```bash
php artisan key:generate
```

## 6. Run Database Migration

```bash
php artisan migrate
```

## 7. Run Development Server

### Option 1 (Linux/macOS)

```bash
composer run dev
```

### Option 2 (Recommended for Windows)

**Terminal 1**

```bash
php artisan serve
```

**Terminal 2**

```bash
npm run dev
```

## 8. Open the Application

```
http://localhost:8000
```

---

# Troubleshooting

## Composer could not find a composer.json file

```
Composer could not find a composer.json file
```

This usually means:

* You are in the wrong directory.
* The Laravel project has not been created yet.
* The repository was not cloned correctly.

Make sure you are inside the project root:

```bash
cd WebDev-Fullstack
```

Verify that `composer.json` exists before running:

```bash
composer install
```

> **Do not run `composer init`.** Laravel projects should always be created using `composer create-project laravel/laravel`.

---

## Project directory is not empty

```
Project directory ".../" is not empty.
```

This error occurs when running:

```bash
composer create-project laravel/laravel .
```

The command installs Laravel into the **current directory**, which must be empty.

Possible solutions:

* Create Laravel in a new directory:

```bash
composer create-project laravel/laravel your-project-name
```

* Or remove/move the existing files before running the command.

---

## Database Connection Error

* Make sure MySQL is running.
* Verify the database credentials in `.env`.
* Ensure the database has already been created.

---

## NPM Installation Error

```bash
rm -rf node_modules package-lock.json
npm install
```

---

## Composer Installation Error

```bash
rm -rf vendor composer.lock
composer install
```

---

# Common Commands

| Command                                                     | Description                              |
| ----------------------------------------------------------- | ---------------------------------------- |
| `composer create-project laravel/laravel .`                 | Install Laravel in the current directory |
| `composer create-project laravel/laravel your-project-name` | Create a new Laravel project directory   |
| `composer install`                                          | Install PHP dependencies                 |
| `npm install`                                               | Install JavaScript dependencies          |
| `composer run dev`                                          | Start Laravel and Vite (Linux/macOS)     |
| `php artisan serve`                                         | Start Laravel server                     |
| `npm run dev`                                               | Start Vite                               |
| `npm run build`                                             | Build frontend assets                    |
| `php artisan migrate`                                       | Run migrations                           |
| `php artisan migrate:fresh`                                 | Recreate all database tables             |
| `php artisan db:seed`                                       | Run database seeders                     |

---

# Development Workflow

Every time you continue development:

**Linux/macOS**

```bash
composer run dev
```

**Windows**

```bash
php artisan serve
```

```bash
npm run dev
```

---

# Production Build

```bash
npm run build
```

---

**Happy Coding! 🚀**
