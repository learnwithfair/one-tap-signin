# GOOGLE SIGN-IN INTEGRATION

[![Youtube][youtube-shield]][youtube-url]
[![Facebook][facebook-shield]][facebook-url]
[![Instagram][instagram-shield]][instagram-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

Thanks for visiting my GitHub account!

A clean and modern e-commerce HTML template integrated with **Google One Tap Sign-In** and **Sign-In with Google Button**.

> This project showcases how to integrate **dual Google authentication** using the latest [Google Identity Services](https://developers.google.com/identity/gsi/web) with full login detection, logout, and UI visibility control.

---

## ✨ Features

- ✅ Google One Tap Sign-In (floating modal)
- ✅ Google Sign-In button (visible UI)
- ✅ Shared login logic using Google Identity Services
- ✅ LocalStorage-based login persistence
- ✅ Auto-hide login UI after successful login
- ✅ Logout button to reset state
- ✅ Fully responsive using Bootstrap 5.3

---

## ⚙️ Technologies Used

- ✅ HTML5, CSS3
- ✅ Bootstrap 5.3
- ✅ Vanilla JavaScript
- ✅ Google Identity Services SDK

---

## 🔐 How It Works

### ✅ 1. Google One Tap Sign-In

- Injected dynamically only when user is **not logged in**
- Uses `google.accounts.id.prompt()` to show the floating modal
- Automatically handles silent login for returning users

### ✅ 2. Sign In With Google Button

- Uses `google.accounts.id.renderButton()` to render a visible Google sign-in button
- When clicked, it authenticates the user and calls the same `handleCredentialResponse()` callback as One Tap

### ✅ 3. After Login

- Stores user info (name, email, picture) in `localStorage`
- Displays a professional top bar with user info and a logout button
- Hides One Tap modal and button
- Prevents Google from auto-triggering One Tap again with `cancel()` and `disableAutoSelect()`

---

## 🚀 How to Use

### ✅ 1. Clone or Download

```bash
git clone https://github.com/yourusername/learn-with-fair-login.git
```

Or just download the `index.html` file and open it in your browser.

---

### ✅ 2. Open in Browser

Simply open the `index.html` file in any modern web browser.

> **⚠️ Note:**  
> Google One Tap **only works on**:
>
> - `http://localhost` — for local development
> - An **HTTPS-secured domain** — for live/production use

---

### ✅ 3. Replace Client ID (Optional but Recommended)

To use your own Google Sign-In credentials, follow these steps:

#### 🔧 Create Your Google OAuth 2.0 Client ID

1. Go to the [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select an existing one
3. Navigate to:  
   **APIs & Services → Credentials**
4. Click **Create Credentials → OAuth client ID**
5. Choose:

   - **Application type**: `Web Application`
   - **Authorized JavaScript origins**:
     - `http://localhost`
     - Or your custom HTTPS domain
   - **Authorized redirect URIs**: _(leave blank)_

6. Click **Create**, and copy your new **Client ID**

---

#### 🧩 Replace the Client ID in the Code

Update both places in your code where `client_id` is set:

```js
const clientId = "YOUR_OWN_CLIENT_ID";

google.accounts.id.initialize({
  client_id: clientId,
  callback: handleCredentialResponse,
  ...
});

google.accounts.id.renderButton(
  document.getElementById("google-button"),
  {
    client_id: clientId,
    ...
  }
);
```

This ensures both One Tap and the Sign-In button use your own credentials.

---

## 🧪 Functional Overview

| Feature                    | Description                                |
| -------------------------- | ------------------------------------------ |
| One Tap Sign-In            | Appears as floating prompt (if logged out) |
| Sign-In with Google Button | Renders below navbar for manual login      |
| Unified Auth Callback      | Both use `handleCredentialResponse()`      |
| Persistent Session         | Stores info in `localStorage`              |
| Logout                     | Clears session, shows login again          |
| Responsive                 | Yes – works on mobile, tablet, desktop     |

## Follow Me

[<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/github.svg' alt='github' height='40'>](https://github.com/learnwithfair) [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/facebook.svg' alt='facebook' height='40'>](https://www.facebook.com/learnwithfair/) [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/instagram.svg' alt='instagram' height='40'>](https://www.instagram.com/learnwithfair/) [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/twitter.svg' alt='twitter' height='40'>](https://www.twiter.com/learnwithfair/) [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/youtube.svg' alt='YouTube' height='40'>](https://www.youtube.com/@learnwithfair)

<!-- MARKDOWN LINKS & IMAGES -->

[youtube-shield]: https://img.shields.io/badge/-Youtube-black.svg?style=flat-square&logo=youtube&color=555&logoColor=white
[youtube-url]: https://youtube.com/@learnwithfair
[facebook-shield]: https://img.shields.io/badge/-Facebook-black.svg?style=flat-square&logo=facebook&color=555&logoColor=white
[facebook-url]: https://facebook.com/learnwithfair
[instagram-shield]: https://img.shields.io/badge/-Instagram-black.svg?style=flat-square&logo=instagram&color=555&logoColor=white
[instagram-url]: https://instagram.com/learnwithfair
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/company/learnwithfair
