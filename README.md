# Joomla! Docker

Deploy a fully functional Joomla! CMS on [42helv.com](https://42helv.com).

## Features

- **One-Click Deploy** - Deploy directly from 42helv.com templates
- **MySQL Database** - Automatically provisioned and configured
- **Apache + PHP** - Optimized configuration for Joomla!
- **SSL Ready** - Works with 42helv.com automatic SSL

## Quick Start

### Deploy on 42helv.com

1. Sign up at [42helv.com](https://42helv.com)
2. Go to **Services** → **Create New**
3. Select the **Joomla!** template
4. Configure your site and deploy

Your Joomla! site will be available at `https://your-site.42helv.com/`

### Initial Setup

After deployment, access the Joomla! admin panel at:
- **Site URL**: `https://your-site.42helv.com/`
- **Admin URL**: `https://your-site.42helv.com/administrator`
- Create your admin account during the installation wizard

## Configuration

The following environment variables are available:

| Variable | Default | Description |
|----------|---------|-------------|
| `JOOMLA_DB_HOST` | (auto) | Database host |
| `JOOMLA_DB_PORT` | `3306` | Database port |
| `JOOMLA_DB_NAME` | `joomla` | Database name |
| `JOOMLA_DB_USER` | (auto) | Database user |
| `JOOMLA_DB_PASSWORD` | (auto) | Database password |

## Local Development

```bash
# Clone the repository
git clone https://github.com/dannysimfukwe/joomla-docker.git
cd joomla-docker

# Start with Docker Compose
docker-compose up -d

# Access Joomla! at http://localhost:8080
```

## Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    Apache (Port 80)                    │
│                    + PHP-FPM                            │
└──────────────────────────┬──────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────┐
│                      Joomla!                           │
│                  (content management)                  │
└──────────────────────────┬──────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────┐
│                   MySQL (Port 3306)                    │
│                   (content database)                    │
└─────────────────────────────────────────────────────────┘
```

## Tech Stack

- [Joomla!](https://www.joomla.org/) - Open-source content management system
- Apache - Web server
- PHP 8.x - Programming language
- MySQL - Database

## Security Notes

1. **Strong password** - Use a strong password during installation
2. **SSL enabled** - Automatic HTTPS via 42helv.com
3. **Keep updated** - Regularly update Joomla! and extensions

## Troubleshooting

### Installation wizard not working?
Verify your `JOOMLA_DB_*` environment variables are correct.

### Database connection issues?
Check that MySQL is accessible and credentials are correct.

### Need to reset?
Delete all files and the database, then redeploy from 42helv.com.

## License

MIT License - Deploy freely on 42helv.com or your own infrastructure.

---

Built with ❤️ on [42helv.com](https://42helv.com)