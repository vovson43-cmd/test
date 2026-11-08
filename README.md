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
