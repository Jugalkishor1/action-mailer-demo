# Action Mailer Demo Project

This is a demo project to showcase the setup and use of Action Mailer in a Ruby on Rails application.

## Requirements

- Ruby 3.2.2 or later
- Rails 7.1.3 or later
- A Gmail account for SMTP settings

## Getting Started

Follow these instructions to get a copy of the project running on your local machine.

### Installation

1. **Clone the repository**:

    ```sh
    git clone https://github.com/Jugalkishor1/action-mailer-demo.git
    cd action-mailer-demo
    ```

2. **Install the required gems**:

    ```sh
    bundle install
    ```

3. **Set up the database**:

    ```sh
    rails db:create
    rails db:migrate
    ```

4. **Set up environment variables**:

    Create a `.env` file in the root directory and add your email credentials:

    ```sh
    touch .env
    ```

    Add the following lines to the `.env` file:

    ```sh
    EMAIL_USER_NAME=your_email@gmail.com
    EMAIL_PASSWORD=your_email_password
    ```

    **Note**: Make sure to add `.env` to your `.gitignore` file to prevent it from being committed to version control.

    ```sh
    echo '.env' >> .gitignore
    ```

5. **Configure SMTP settings**:

    Ensure your `config/environments/development.rb` file includes the SMTP settings:

    ```ruby
    config.action_mailer.delivery_method = :smtp
    config.action_mailer.smtp_settings = {
      address: "smtp.gmail.com",
      port: 587,
      user_name: ENV['EMAIL_USER_NAME'],
      password: ENV['EMAIL_PASSWORD'],
      authentication: "plain",
      enable_starttls_auto: true
    }
    config.action_mailer.default_url_options = { host: 'localhost:3000', protocol: 'http' }
    ```

### Usage

1. **Start the Rails server**:

    ```sh
    rails server
    ```

2. **Create a new user**:

    Navigate to `http://localhost:3000` and fill out the form to create a new user. An email will be sent to the provided email address upon successful creation.


## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## Acknowledgments

- Thanks to the Rails community for providing great documentation and resources.
