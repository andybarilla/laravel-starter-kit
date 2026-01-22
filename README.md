# Laravel Livewire Starter Kit

A Laravel starter kit with Livewire, Flux UI, Fortify authentication, and Horizon queue management.

## What's Included

- **Laravel 12** - The latest Laravel framework
- **Livewire 4** - Full-stack framework for Laravel
- **Flux UI** - Tailwind CSS component library for Livewire
- **Laravel Fortify** - Headless authentication backend
- **Laravel Horizon** - Redis queue dashboard
- **Tailwind CSS 4** - Utility-first CSS framework
- **Pest** - Testing framework
- **Pint** - Code style fixer
- **Larastan** - Static analysis

## Installation

### Using the Laravel Installer

```bash
laravel new my-app --using=github:andybarilla/laravel-starter-kit
```

After installation, install frontend dependencies and build assets:

```bash
cd my-app
npm install
npm run build
```

### Manual Installation

```bash
git clone https://github.com/andybarilla/laravel-starter-kit.git my-app
cd my-app
composer install
cp .env.example .env
php artisan key:generate
touch database/database.sqlite
php artisan migrate
npm install
npm run build
```

## Development

Start the development server with all services:

```bash
composer run dev
```

This runs concurrently:
- Laravel development server
- Queue worker
- Pail log viewer
- Vite dev server

Or run services individually:

```bash
php artisan serve      # Laravel server
npm run dev            # Vite dev server
php artisan queue:work # Queue worker
```

## Testing

```bash
php artisan test
```

## Code Quality

```bash
# Fix code style
composer run lint

# Static analysis
./vendor/bin/phpstan analyse
```

## Horizon (Queue Dashboard)

Horizon requires Redis. Configure your Redis connection in `.env`:

```env
QUEUE_CONNECTION=redis
REDIS_HOST=127.0.0.1
REDIS_PORT=6379
```

Access the dashboard at `/horizon`.

## License

MIT
