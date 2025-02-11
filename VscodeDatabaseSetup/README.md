# Database Setup Requirements for VSCode

## Required VSCode Extensions
1. **SQLTools**: Main database management extension
   - Supports multiple databases (MySQL, PostgreSQL, SQLite, etc.)
   - Query execution and results viewing
   - Auto-completion and IntelliSense

2. **Download These Extensions**:
   - Database Client JDBC
   - Database Client

## Additional Tools

1. **Database GUI Client** (Optional but recommended):
   - DBeaver (Free, multi-platform)
   - MySQL Workbench (For MySQL)
   - pgAdmin (For PostgreSQL)

2. **Database Server**:
   - MySQL Server
   - PostgreSQL Server
   - SQLite (No server needed, file-based)

## VSCode Settings

Add these to your VSCode settings.json:
```json
{
    "sqltools.connections": [],
    "sqltools.useNodeRuntime": true,
    "sqltools.format": {
        "uppercase": true,
        "linesBetweenQueries": 2
    }
}
```

## Connection Setup Steps

1. Install required database extension
2. Press `Ctrl/Cmd + Shift + P`
3. Type "SQLTools Connection"
4. Select "Add New Connection"
5. Follow the connection wizard:
   - Choose database type
   - Enter connection details (host, port, username, password)
   - Test connection
   - Save connection

## Security Best Practices

1. Never commit database credentials to version control
2. Use environment variables for sensitive information
3. Set up proper user permissions in your database
4. Keep your database drivers and extensions updated

## Troubleshooting

1. Ensure database server is running
2. Verify connection credentials
3. Check firewall settings
4. Confirm database port is accessible
5. Review VSCode extension logs for errors