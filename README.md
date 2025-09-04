# 🥋 Cloud Run Basic – Full Summary
# Initial code from Aaron McDonald and T.I.Q.S. - thank you Gentlemen!


![GCP](https://img.shields.io/badge/cloud-Google%20Cloud-blue)
![Cloud Run](https://img.shields.io/badge/service-Cloud%20Run-success)
![Build](https://img.shields.io/badge/build-passing-brightgreen)
![Python](https://img.shields.io/badge/python-3.13-blue)
![Flask](https://img.shields.io/badge/framework-Flask-red)
![Status](https://img.shields.io/badge/status-Deployed-success)
![Version](https://img.shields.io/badge/version-v2.0-yellow)
![GitHub Repo Size](https://img.shields.io/github/repo-size/https://github.com/jastek69/gcp-cloudrun-basic.git)
![Last Commit](https://img.shields.io/github/last-commit/https://github.com/jastek69/gcp-cloudrun-basic.git)

> Deploy a dynamic Python Flask app to Google Cloud Run with traffic splitting, environment configs, and CI/CD via Cloud Build and GitHub triggers.

This guide walks through the deployment of a Flask application to **Google Cloud Run**, with **Cloud Build triggers**, **revision rollouts**, and **traffic splitting** using the `gcloud` CLI and GitHub integration.

---

## 🧭 Project Summary

The **gcp-cloudrun** project is a Python Flask-based web application deployed to **Google Cloud Run** using a CI/CD workflow powered by **Google Cloud Build** and **GitHub**. The application is structured around a dual-branch deployment strategy, where versioned branches (`be-a-man-level-10-v1` and `be-a-man-level-10-v2`) represent distinct revisions of the application. These revisions are built and deployed either manually via the `gcloud run deploy` CLI or automatically via GitHub-triggered Cloud Build pipelines.

The app dynamically renders content based on environment variables, which are configured at deployment time. Once deployed, revisions can be managed through **Cloud Run traffic splitting**, allowing the developer to direct specific percentages of user traffic to different versions of the service (e.g., **50/50 rollout**). This enables controlled testing, rollback, and revision monitoring without downtime. The architecture is lightweight, serverless, and regionally deployed in `asia-northeast1`, leveraging Google's managed infrastructure for scalability and security.

---

## 📚 References & Documentation

- **Cloud Run:**
  - [Allowing Unauthenticated Access](https://cloud.google.com/run/docs/authenticating/public)  
  - [Cloud Run Environment Variable Behavior](https://cloud.google.com/run/docs/configuring/environment-variables)  
  - [Cloud Run IAM Permissions](https://cloud.google.com/run/docs/securing/managing-access)  
  - [Cloud Run Traffic Splitting](https://cloud.google.com/run/docs/rollouts-rollbacks-traffic-migration)  

- **Cloud Build:**
  - [Connect GitHub to Cloud Build](https://cloud.google.com/build/docs/automating-builds/github/connect-repo-github)  
  - [Deploying Services to Cloud Run](https://cloud.google.com/run/docs/deploying)  
  - [Deploying to Cloud Run with Cloud Build](https://cloud.google.com/build/docs/deploying-builds/deploy-cloud-run)  

- **Flask:**
  - [Flask Documentation](https://flask.palletsprojects.com/en/stable/)  

- **Google Cloud SDK References:**
  - [gcloud builds triggers create github](https://cloud.google.com/sdk/gcloud/reference/builds/triggers/create/github)  
  - [gcloud run deploy](https://cloud.google.com/sdk/gcloud/reference/run/deploy)  
  - [gcloud run services describe](https://cloud.google.com/sdk/gcloud/reference/run/services/describe)  
  - [gcloud run services update-traffic](https://cloud.google.com/sdk/gcloud/reference/run/services/update-traffic)  

- **GitHub:**
  - [Git - The Simple Guide](https://rogerdudler.github.io/git-guide/)  
  - [Git Branching and Merging](https://www.atlassian.com/git/tutorials/using-branches)  
  - [GitHub Docs – About repositories](https://docs.github.com/en/repositories)  
  - [GCP Cloud Builders (GitHub Repo)](https://github.com/GoogleCloudPlatform/cloud-builders/tree/master/gcloud)  

- **Python:**
  - [python-dotenv (GitHub Repo)](https://github.com/theskumar/python-dotenv)  
  - [Using `.env` Files in Flask Apps](https://flask.palletsprojects.com/en/latest/config/#environment-and-dotenv-files)  
  - [Building a Cloud Build Configuration YAML](https://cloud.google.com/build/docs/build-config-file-schema)  
  - [Using `os.environ` in Python](https://docs.python.org/3/library/os.html#os.environ)

---

## 🌿 Repository Branches - WIP not implemented yet

The GitHub repo `https://github.com/jastek69/gcp-cloudrun-basic.git` contains two main branches:

### 🔹 [`be-a-man-level-10-v1`](https://github.com/https://github.com/jastek69/gcp-cloudrun-basic.git/tree/gcp-cloudrun-v1)

- Basic Flask app  
- Default environment values  
- Cloud Run v1 deployable

### 🔹 [`be-a-man-level-10-v2`](https://github.com/https://github.com/jastek69/gcp-cloudrun-basic.git/tree/gcp-cloudrun-v2)

- Enhanced content via environment vars (e.g., `"Fight Smith Til The End"`)
- Includes `cloudbuild.yaml` for automated builds  
- Ready for second Cloud Run revision and traffic split

---

## ❗ Troubleshooting

| Issue | Solution |
|-------|----------|
| `source URL not found` | Use `--source=.` with a **local clone** |
| `beta command not found` | Run Google Cloud SDK Shell as Admin and install with `gcloud components install beta` |
| `no connected repo` | Use Cloud Console to connect GitHub via Cloud Build |
| `invalid revision name` | List actual revisions with `gcloud run revisions list` |
| `traffic split fails` | Ensure **2+ revisions exist**, and revision names match exactly |

---

## ✍️ Authors & Acknowledgments

- **Author:** John Sweeney
- **Original Code:** T.I.Q.S. and Aaron McDonald

---
