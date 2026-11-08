Here is the complete step-by-step procedure to delete your local Git setup, create a fresh GitHub repository, set up your Personal Access Token, and push your code via HTTPS.

1. **Clean up local Git folder:** 10 seconds.
Reset your local folder so you start completely fresh:

```bash
rm -rf .git

```

*Verification:* Run `ls -a` and confirm the `.git` folder is no longer listed.


2. **Create a new repository on GitHub:** 1 minute.
1. Go to **[GitHub](https://github.com)** in your browser and sign in to **`vovson43-cmd`**.
2. Click the **`+`** icon in the top-right corner and select **New repository**.
3. Enter a repository name (e.g., `MIDTEST`).
4. Leave **Initialize this repository with** unchecked (do **not** check Add a README file).
5. Click **Create repository**.
*Verification:* GitHub opens your new, empty repository page showing quick setup instructions starting with `[https://github.com/vovson43-cmd/](https://github.com/vovson43-cmd/)...`.


3. **Generate a Personal Access Token (PAT):** 1 minute.
1. Click your profile picture in the top-right corner > **Settings**.
2. Scroll down the left sidebar to **Developer settings** > **Personal access tokens** > **Tokens (classic)**.
3. Click **Generate new token** > **Generate new token (classic)**.
4. Set a note name (e.g., `MacBook`), set an expiration, and check the **`repo`** checkbox.
5. Click **Generate token** at the bottom and copy the token string (starts with `ghp_`).
*Verification:* You have copied your token string starting with `ghp_` to your clipboard.


4. **Clear macOS cached credentials:** 10 seconds.
Remove any cached credentials from previous logins so macOS doesn't send old account keys:

```bash
printf "protocol=https\nhost=github.com\n" | git credential reject

```

*Verification:* The command completes silently without error.


5. **Initialize local Git repo & add files:** 30 seconds.
Run these commands in your VS Code terminal:

```bash
git init
git branch -M main
git add .
git commit -m "Initial commit"

```

*Verification:* Terminal outputs `[main (root-commit) ...] Initial commit` with your files listed.


6. **Link remote repository & push code:** 30 seconds.
Link your local repo using your HTTPS URL and push:

```bash
git remote add origin https://github.com/vovson43-cmd/MIDTEST.git
git push -u origin main

```

When prompted by the terminal or pop-up:

* **Username:** `vovson43-cmd`
* **Password:** Paste your **Personal Access Token** (`ghp_...`)
*Verification:* Terminal displays `Branch 'main' set up to track remote branch 'main' from 'origin'`, and refreshing your repository page on GitHub shows all your project files.

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






- [ ] ng new UTS272102692
- [ ] Move assets to public
- [ ] cd UTS272102692

- [ ] Configure src/index.html & CDNs
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>UTS272102692</title>
  <base href="/">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="icon" type="image/x-icon" href="favicon.ico">

  <!-- Google Font: Source Sans Pro -->
  <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Source+Sans+Pro:300,400,400i,700&display=fallback">
  <!-- Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
  <!-- AdminLTE CSS -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/admin-lte@3.2/dist/css/adminlte.min.css">
</head>
<body class="hold-transition sidebar-mini">
  <app-root></app-root>

  <!-- jQuery -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
  <!-- Bootstrap 4 -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/bootstrap/4.6.1/js/bootstrap.bundle.min.js"></script>
  <!-- AdminLTE App -->
  <script src="https://cdn.jsdelivr.net/npm/admin-lte@3.2/dist/js/adminlte.min.js"></script>
</body>
</html>

- [ ] ng g c header header/sidebar/ecommerce/footer 
- [ ] Update src/styles.css 
app-header, app-sidebar, app-ecommerce, app-footer { 
	display: contents; 
} 
- [ ] Update src/app/app.ts
import { Component, signal } from '@angular/core';
import { RouterOutlet } from '@angular/router';
import { Header } from './header/header';
import { Sidebar } from './sidebar/sidebar';
import { Ecommerce } from './ecommerce/ecommerce';
import { Footer } from './footer/footer';

@Component({
  imports: [RouterOutlet, Header, Sidebar, Ecommerce, Footer],
  selector: 'app-root',
  styleUrl: './app.css',
  templateUrl: './app.html',
})
export class App {
  protected readonly title = signal('UTS272102692');
}

- [ ] Copypaste each component by inspect
- [ ] change path for img source, del dist replace with assets
- [ ] asemble with src/app/app.html
<div class="wrapper">
  <app-header></app-header>
  <app-sidebar></app-sidebar>
  <app-ecommerce></app-ecommerce>
  <app-footer></app-footer>
</div>
