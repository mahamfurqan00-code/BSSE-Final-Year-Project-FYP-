# BSSE-Final-Year-Project-FYP-
# Detecting Fraud Apps Using Sentiment Analysis

**Detecting Fraud Apps Using Sentiment Analysis** is a web-based application developed to help identify potentially fraudulent mobile applications by analyzing user reviews, ratings, and feedback. The project belongs to the **NLP (Natural Language Processing) / Information Retrieval** domain.

With the increasing number of applications available online, it can be difficult for users to determine whether an application is genuine or fraudulent based only on existing reviews. This system collects reviews from registered users and applies **sentiment analysis** to identify whether comments are **positive, negative, or neutral**. The analyzed reviews and ratings provide useful insights that help the administrator evaluate an application and determine whether it is likely to be genuine or fraudulent.

### Key Features

- **Admin Module**
  - Add and manage applications with details such as name, link, description, category, image, and rating.
  - Review application details, ratings, and user comments.
  - Analyze user reviews to help detect potentially fraudulent applications.
  - View registered users and their feedback.
  - Monitor reviews using opinion mining and sentiment analysis.

- **User Module**
  - User registration and secure login.
  - Browse applications by different categories.
  - View application details, ratings, and comments.
  - Submit reviews and comments about applications.
  - Provide feedback about the system.

### Sentiment Analysis

The system uses **opinion mining/text analysis** techniques to analyze submitted reviews and classify their sentiment as **positive, negative, or neutral**. The sentiment results can assist the administrator in evaluating the credibility of an application.

### Technologies & Tools

- Python / Visual Studio
- SentiWordNet Dictionary
- WAMP Server
- MySQL 5.6
- Apache/Nginx
- Notepad++

This project demonstrates the practical application of **Natural Language Processing, sentiment analysis, user-generated reviews, and web application development** to support fraud-app detection.

## Deploying on Vercel

This is a Flask application, not a static site. Vercel detects the Flask app in
the root `app.py`; it does not require a root-level `index.html`. The homepage
route renders `templates/welcome.html`.

1. Sign in to Vercel using the GitHub account that can access this repository.
   If the repository is not listed when importing a project, grant the Vercel
   GitHub App access to `mahamfurqan00-code/BSSE-Final-Year-Project-FYP-` in
   GitHub's installed-app settings, then refresh Vercel's import list.
2. In Vercel, choose **Add New → Project**, import
   `mahamfurqan00-code/BSSE-Final-Year-Project-FYP-`, and keep **Root Directory**
   set to the repository root. Leave the build and output directory settings at
   their defaults; Vercel detects the Flask app in `app.py` and installs
   dependencies from `requirements.txt`.
3. Provision a persistent PostgreSQL database, for example through a Vercel
   Marketplace database integration. In the Vercel project settings, add these
   environment variables for the environments you will deploy:
   - `DATABASE_URL`: the PostgreSQL connection URL from your database provider.
   - `SECRET_KEY`: a long, random secret value.
   - `ADMIN_SIGNUP_CODE`: a private admin registration code.
4. Initialize the database once from a local checkout, using the same
   PostgreSQL URL configured in Vercel. Install the packages from
   `requirements.txt`, set `DATABASE_URL` in your terminal, then run:

   ```text
   flask --app app.py init-db
   ```

5. Click **Deploy** in Vercel. Later pushes to the connected `main` branch will
   trigger new deployments. Register your admin account using the
   `ADMIN_SIGNUP_CODE` value.

Do not use the default SQLite database for a Vercel deployment: Vercel Functions
do not provide persistent local storage, so SQLite data would not reliably
survive across invocations. Keep database URLs and secrets in environment
variables; do not commit them.
