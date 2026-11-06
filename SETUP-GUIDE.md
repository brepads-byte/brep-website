# Brep website: setup and editing guide

This guide covers two things:

1. **One-time setup** (about 45 minutes): put the website online at brep.co.in and turn on the editor.
2. **Everyday editing**: add projects, change photos and update text yourself, without a developer.

Everything here uses free accounts:

- **GitHub** stores the website files.
- **Netlify** puts the website online and delivers enquiry-form messages.
- **Sveltia CMS** is the editing screen, at brep.co.in/admin.

---

## What's in the website folder

| Folder or file | What it is |
|---|---|
| `index.html` | The website design. You don't need to touch this. |
| `content/` | All the text and project details. The editor changes these files for you. |
| `images/uploads/` | All the photos. Photos you upload in the editor are saved here. |
| `admin/` | The editor. `admin/config.yml` holds its settings. |
| `images/favicon.svg` | The red-dot icon shown in browser tabs. |

---

## Part 1: One-time setup

### Step 1. Create a GitHub account

1. Go to github.com and choose **Sign up**. Use the studio's email address.
2. Pick a username, for example `brep-studio`. Write it down, because you'll need it in step 3.

### Step 2. Put the website files on GitHub

1. On GitHub, click **+** (top right), then **New repository**.
2. Fill it in:
   - **Repository name:** `brep-website`
   - **Visibility:** Private is fine.
   - Tick **Add a README file**.
3. Click **Create repository**.
4. On the new repository page, click **Add file**, then **Upload files**.
5. Unzip `brep-website.zip` on your computer. Open the unzipped folder, select everything inside it (`index.html`, `admin`, `content`, `images` and this guide) and drag it all onto the GitHub upload page.
   - Drag the items *inside* the folder, not the folder itself.
6. Click **Commit changes**.

### Step 3. Tell the editor where your files are

1. In the repository, open the `admin` folder, then `config.yml`.
2. Click the pencil icon to edit it.
3. Find this line:
   ```
   repo: YOUR-GITHUB-USERNAME/brep-website
   ```
4. Replace `YOUR-GITHUB-USERNAME` with your username, for example:
   ```
   repo: brep-studio/brep-website
   ```
5. Click **Commit changes**.

### Step 4. Put the site online with Netlify

1. Go to netlify.com and choose **Sign up**, then **Sign up with GitHub**.
2. Click **Add new site**, then **Import an existing project**, then **GitHub**.
3. Allow Netlify to see your repositories, then choose `brep-website`.
4. Leave **Build command** empty and leave **Publish directory** empty.
5. Click **Deploy**.

After about a minute your site is live at an address like `something.netlify.app`. Open it to check.

### Step 5. Turn on the enquiry form

1. In Netlify, open your site, then **Forms**.
2. Click **Enable form detection**.
3. Go to **Deploys**, then **Trigger deploy**, then **Deploy site**. This lets Netlify find the form.
4. Back in **Forms**, open **Form notifications**. Add an **Email notification** to `brep.ads@gmail.com`.

Enquiries from the Contact page will now arrive in your inbox. Netlify's free plan includes 100 form messages a month.

### Step 6. Let yourself log in to the editor

The editor signs you in with your GitHub account. This takes two short steps.

**A. Create a GitHub login app**

1. On GitHub, click your profile picture, then **Settings**.
2. Scroll down to **Developer settings**, then **OAuth Apps**, then **New OAuth App**.
3. Fill it in:
   - **Application name:** Brep website editor
   - **Homepage URL:** `https://brep.co.in`
   - **Authorization callback URL:** `https://api.netlify.com/auth/done`
4. Click **Register application**.
5. Copy the **Client ID**.
6. Click **Generate a new client secret** and copy the secret too.

**B. Give those to Netlify**

1. In Netlify, open your site, then **Site configuration**.
2. Open **Access & security** (older menus call it **Access control**), then **OAuth**.
3. Under **Authentication providers**, click **Install provider**.
4. Choose **GitHub**, paste the Client ID and secret, and save.

**Test it**

1. Go to `your-site.netlify.app/admin` and click **Sign in with GitHub**.
2. You should see **Projects** and **Pages**.

If your editor's login screen offers **Sign in with token** instead, you can create a token rather than doing A and B:

1. On GitHub, go to **Settings**, then **Developer settings**, then **Personal access tokens**, then **Fine-grained tokens**, then **Generate new token**.
2. Fill it in:
   - **Repository access:** only `brep-website`.
   - **Permissions:** set **Contents** to **Read and write**.
3. Generate the token, copy it and paste it into the editor.
4. Keep the token private, like a password.

### Step 7. Connect brep.co.in

Before you start, two checks:

- **Talk to whoever built the current site.** Switching the domain replaces the old site.
- **Download the Aarif Adobe photos first.** The old site keeps them on a photo service the old developer controls, so you need your own copies before switching.

Then connect the domain:

1. In Netlify, open your site, then **Domain management**, then **Add a domain**, and enter `brep.co.in`.
2. Netlify shows you the exact DNS settings to add. Usually that's an **A record** and a **CNAME record** for `www`.
3. Log in where you bought brep.co.in (for example GoDaddy, BigRock or Hostinger). Open the domain's **DNS settings** and add exactly what Netlify shows.
4. Wait. It usually takes under an hour, and can take up to a day.

Netlify adds the secure padlock (https) automatically. Once it's done, your editor is at **brep.co.in/admin**.

If you used the GitHub login app in step 6, update its **Homepage URL** to `https://brep.co.in` if you changed anything.

---

## Part 2: Everyday editing

Go to **brep.co.in/admin** and sign in. You'll see two sections:

- **Projects:** every project on the website.
- **Pages:** the Studio About, Services and Process pages, and your contact details.

Every time you click **Save**, the website updates by itself within about a minute.

### Add a new project

1. Click **Projects**, then **All projects**.
2. Click **Add Project**. It appears at the bottom of the list.
3. Fill in the fields:
   - **Project name**, for example *Riverside House*.
   - **Category:** Residential, Commercial, Hospitality or Interiors. This decides which menu it appears under.
   - **Type**, for example *Residence*.
   - **Location**, for example *Erode*.
   - **Area**, for example *4,500 sq ft*.
   - **Description:** about 100 words. Anything longer is cut off on the site.
4. Under **Photos**, click **Add Photo** and upload a photo. Repeat for each one (3 to 6 photos works well).
   - The **first photo** is the one shown in the home-page slideshow.
5. Leave **Sample project** switched off.
6. Click **Save**.

### Change the order of projects

Drag projects up or down in the list, then click **Save**. On the website, projects are always grouped by category (Residential first, then Commercial, Hospitality and Interiors). Within each category they follow your order.

### Remove a sample project

Open the project and click the **⋮** menu or the bin icon next to it, then click **Save**.

The website currently has 11 sample projects (everything except Aarif Adobe). Replace or remove them as you add real work.

### Change photos

Open the project, page or service. Remove a photo with its bin icon and add a new one with **Add Photo**. Drag photos to reorder them, then click **Save**.

### Edit the Studio, Services and Process pages

Under **Pages**:

- **Studio · About:** the title, paragraphs, team members and the photos that scroll under the logo. Leave the photo list empty to keep the line drawings.
- **Studio · Services:** each service's name, description and up to 4 photos.
- **Studio · Process:** the stages. They are numbered automatically in the order you put them.
- **Contact details:** address, phone, WhatsApp number, email and Instagram. These update the Contact page and the sidebar icons.

### Photo tips

- Use JPG photos about 2,000 pixels on the long side and under 1 MB each, so the site stays fast. Most phones and editing apps can export at this size.
- Landscape and portrait photos both work. The gallery shows each photo in its own shape.
- Name files simply before uploading, for example `riverside-house-1.jpg`.

---

## What the editor can't change

The editor changes **content**: text, photos, projects and contact details. It doesn't change the **design**: layout, fonts, colours, the menu, the logo animation on the About page, or the red-dot details. Those live in `index.html`, so for design changes ask a developer, or ask Claude with the file.

## If something goes wrong

- **Editor shows "Not Found" or won't log in.** Check that `admin/config.yml` has your exact GitHub username (step 3), and that step 6 is done.
- **A change doesn't show on the site.** Wait a minute, then refresh. In Netlify, **Deploys** shows whether the latest update finished.
- **You made a mistake and want the old version back.** On GitHub, every save is kept. Open the `content` file, click **History**, and you can see or copy any earlier version.
