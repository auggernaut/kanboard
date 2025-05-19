Kanboard
========

Kanboard is project management software that focuses on the Kanban methodology.

**This application is in maintenance mode**. What does it mean?

Citing [Wikipedia](https://en.wikipedia.org/wiki/Maintenance_mode):

> In the world of software development, maintenance mode refers to a point in a computer program's life when it has reached all of its goals and is generally considered to be "complete" and bug-free. The term can also refer to the point in a software product's evolution when it is no longer competitive with other products or current with regard to the technology environment it operates within.

- The [author](#credits) of this application is not actively developing any new major features (only small fixes)
- New releases are published regularly depending on the contributions made by the community
- Pull requests for new features and bug fixes are accepted as long as the [guidelines](.github/pull_request_template.md) are followed

Table of Contents
-----------------

- Official website: <https://kanboard.org/>
- [List of features](https://kanboard.org/#features)
- [Change Log](https://github.com/kanboard/kanboard/blob/main/ChangeLog)
- [Forum](https://kanboard.discourse.group/)
- Official documentation: <https://docs.kanboard.org/>
    - [Requirements](https://docs.kanboard.org/v1/admin/requirements/)
    - [Installation instructions](https://docs.kanboard.org/v1/admin/installation/)
    - [Upgrade to a new version](https://docs.kanboard.org/v1/admin/upgrade/)
    - [Use Kanboard with Docker](https://docs.kanboard.org/v1/admin/docker/)

Deploying to Fly.io
---------------------

1.  **Install `flyctl`**: Follow the instructions on the [official Fly.io documentation](https://fly.io/docs/hands-on/install-flyctl/).
2.  **Login to Fly.io**: Run `flyctl auth login`.
3.  **Launch the app**: Navigate to your Kanboard project directory in your terminal and run `flyctl launch`. This will detect the `fly.toml` file and guide you through the initial deployment. You might need to adjust the generated `fly.toml` based on your specific needs (e.g., for persistent storage, environment variables).
4.  **Deploy changes**: After making changes to your application, deploy them by running `flyctl deploy`.

Running Locally (for development)
---------------------------------

1.  **Prerequisites**:
    *   Install [PHP](https://www.php.net/manual/en/install.php) (version compatible with Kanboard, check `composer.json`).
    *   Install [Composer](https://getcomposer.org/doc/00-intro.md).
2.  **Install Dependencies**:
    *   Navigate to your Kanboard project directory.
    *   Run `composer install` to download the required PHP libraries.
3.  **Configuration**:
    *   If it doesn't exist, copy `config.default.php` to `config.php`.
    *   Modify `config.php` to set up your database connection (e.g., for SQLite, which is simplest for local development) and other parameters as needed.
    *   Ensure the `data` directory (and `plugins`, `certs` if used) are writable by the web server/PHP process.
4.  **Database Migration**:
    *   Run `php cli db:migrate` to set up the database schema.
5.  **Compile Assets**:
    *   Run `php cli css` to compile CSS files.
    *   Run `php cli js` to compile JavaScript files.
6.  **Start the PHP Built-in Web Server**:
    *   Run `php -S localhost:8000` (or your preferred port) from the project root.
    *   Access Kanboard in your browser at `http://localhost:8000`.

Credits
-------

- Main developer: Frédéric Guillot
- [Contributors](https://github.com/kanboard/kanboard/graphs/contributors)
- Distributed under [MIT License](https://github.com/kanboard/kanboard/blob/main/LICENSE)
