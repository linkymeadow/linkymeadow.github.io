# Agent Instructions

## Project

- This is an operations notice site built with HTML and CSS for GitHub Pages. There is no build step.
- `public/index.html` contains notices and metadata, `public/styles.css` defines the presentation, and `public/assets/images/` contains images for deployment.
- Keep deployable static files in `public/`. The workflow in `.github/workflows/pages.yml` uploads only this directory. Keep documentation, repository configuration, and working files outside it.
- Use `public/` as the document root when previewing the site locally.
- The operations notice URL is `https://linkymeadow.github.io/`. The main site is `https://www.linkymeadow.com/`.

## Scope of Changes

- Change only what the user requests. Do not add unrequested features, frameworks, JavaScript, APIs, or build dependencies.
- Preserve existing changes. Do not modify other repositories or service settings without a separate request.
- Use the Korean term “운영 공지” (operations notices) in user-facing copy. Preserve mobile readability, vertical lists, and both light and dark themes.
- Read `DESIGN.md` before changing the interface or social sharing images. Update that document when design decisions change.
- Keep the public `README.md` limited to the site introduction and official URL. Do not add internal procedures or agent instructions.

## Notices and Links

- Notices are updated manually by the operator. Do not present “공지 없음” (no notices) as confirmation of normal operation or a real-time status check.
- When publishing or editing an actual notice, update its status, title, body, displayed timestamp, and `datetime` together. Use Korea Standard Time.
- Do not change the notice timestamp when only design or metadata changes.
- Display the main site address above the operations notice address. Preserve `target="_blank"` and `rel="noopener noreferrer"` on the main site link.
- Remove the `main-site-address` row when posting a notice that the main domain cannot be trusted. Do not add automatic redirects.
- When changing the canonical URL, check the related URLs in the canonical link, OG tags, `robots.txt`, and `sitemap.xml` together.

## Images and Public Files

- Use 1200×630 JPEGs for OG images. Do not add text to generated images. If text is separately requested, prioritize the domain over the site name.
- Use Sharp for image processing. After resizing, verify metadata removal and inspect image quality. Do not overwrite the source image.
- Keep generated source images, prompts, verification screenshots, and other working files in the Git-ignored `.artifacts/` directory. Include only deployment assets in public files.
- Do not include credentials, personal contact details, local absolute paths, or internal logs in public files.

## Validation and Git

- For interface changes, check line wrapping, horizontal overflow, and link behavior on mobile and desktop. Check color changes in both light and dark themes.
- For image or metadata changes, verify file paths, image dimensions, and consistency with OG tags. Do not add unnecessary browser checks or tests for documentation-only changes.
- Do not change Git state when the user only requests a commit plan or message recommendation. Commit and push only within the requested scope, and stage the intended files explicitly.
- Distinguish verified results from anything that could not be verified when reporting your work.
