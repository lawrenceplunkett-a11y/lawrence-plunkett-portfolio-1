LAWRENCE PLUNKETT PORTFOLIO — FTP STARTER
========================================

THIS PACKAGE IS A STATIC FRONT-END PROTOTYPE.
It is suitable for local editing and static hosting. It does NOT yet include
secure reference management, a CMS, a database, login, or a production API.

FOLDER MAP
----------
index.html                  Website entry point
assets/css/styles.css       Visual design and responsive layout
assets/js/script.js         Navigation, filters, case-study and CV interactions
assets/images/              Add original images here
  projects/                  Project and case-study images
  profile/                   Profile portrait
  icons/                     Favicons and interface icons
downloads/                   Optional public CV or downloadable portfolio files
docs/                        Build notes and implementation plan

LOCAL PREVIEW
-------------
Open index.html in a browser, or run a local server from this folder:

  python3 -m http.server 8000

Then visit http://localhost:8000

EDITING
-------
1. Edit index.html for page content and structure.
2. Edit assets/css/styles.css for typography, colour, spacing and layout.
3. Edit assets/js/script.js for interactions.
4. Put project images in assets/images/projects/ and reference them with paths
   such as assets/images/projects/project-name.jpg.
5. Keep filenames lowercase and use hyphens, e.g. haier-campaign-hero.jpg.
6. Keep an untouched backup before each upload.

FTP / SFTP UPLOAD
-----------------
Upload the CONTENTS of this folder (not the enclosing folder itself) into the
website document root supplied by your hosting provider. Common roots include
public_html, httpdocs, www, or a domain-specific web root. Confirm the correct
root with your host; do not assume its name.

The server should end up with:
  web-root/
    index.html
    assets/
      css/styles.css
      js/script.js
      images/...

Upload index.html and the assets folder together. Preserve the folder names.
Use SFTP where available rather than unencrypted FTP. Do not upload private
reference information, passwords, API keys, draft CVs, or confidential files.

VERSIONING / ROLLBACK
--------------------
Before changing the live site, download a copy of the current web root or
create a dated local backup. Suggested labels:
  backups/2026-11-06-before-edit/
  releases/2026-11-06-v1/

For a small change, upload changed files only. For a full release, upload the
complete site and check the homepage, navigation, project filters, career tabs,
print-CV action and mobile layout. Keep the previous release so you can restore
it if anything breaks.

IMPORTANT PRODUCTION NOTES
--------------------------
- Replace placeholder email and LinkedIn links before launch.
- Verify career dates, qualifications, project details and claims.
- Replace illustrative project cards with authorised original work.
- The current reference area is a public display placeholder only.
- Never collect real referee details through this static prototype.
- A secure reference portal requires a backend, authentication, access control,
  consent tracking, protected storage and server-side validation.
- The interactive CV currently uses the browser print/save-to-PDF function.

DOMAIN / HTTPS
--------------
Point the domain to the hosting provider and enable its SSL certificate / HTTPS.
Use the host's control panel for DNS and document-root configuration.
