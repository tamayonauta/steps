# Setup CI/CD GitLab and Heroku for Django and Postgis

## Setup Heroku app

1. Create heroku app
1. Add Postgres DB add-on
1. Set environment vars

## Setup Heroku DB

1. Enable Postgis:

    ```bash
    heroku pg:psql
    ```

    ```bash
    CREATE EXTENSION postgis;
    ```

1. Set Heroku environment var:

    ```bash
    heroku config:set BUILD_WITH_GEO_LIBRARIES=1
    ```

## Setup heroku file

1. Copy [heroku.yml](heroku.yml) file and paste it into your project root
1. Update content

## Setup deployment-tasks file

1. Copy [deployment-tasks.sh](deployment-tasks.sh) file and paste it into your project root
1. Update content

## Save Heroku API Key in GitLab

1. Go to **Heroku > Account settings > API Key**
1. Reveal for show API Key value
1. Go to **GitLab > Settings > CI / CD > Variables**
1. Set variable key: HEROKU_API_KEY
1. Set variable value: <YOUR_HEROKU_API_KEY>
1. Save

## Install GitLab Runner

1. Go to **Settings > CI / CD > Runners**
1. Follow steps of **Setup a specific Runner manually**

## Setup .gitlab-ci file

1. Copy [.gitlab-ci.yml](.gitlab-ci.yml) file and paste it into your project root
1. Update content

## Push commit to master for run pipeline

## References

[CI/CD Workflow reference](/ci-cd/CI-CD-Workflow.jpg)