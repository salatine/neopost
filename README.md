# neopost
*neopost* is a minimalist, customizable theme for personal blogs, inspired by the aesthetics of neocities. it allows for multilingual, flexible content management and easy customization of styles through simple configuration.
![neopost example site, with the "light-blue" variant theme.](https://raw.githubusercontent.com/salatine/neopost/main/images/screenshot.png)
this example site is available at [neopost.neocities.org](https://neopost.neocities.org).

## installation & quickstart
```bash
hugo new site my-site
cd my-site
git clone "https://github.com/salatine/neopost.git" themes/neopost

# copy over the hugo configuration file
cp themes/neopost/example/hugo-en.toml hugo.toml

# create the post (edit it later yourself ok)
hugo new content/posts/new-post.md

# run the server and see it!
hugo serve

```

## configuration

Your configuration is set in the `hugo.yaml` or `hugo.toml` file.

If you aren't familiar with either formats, prefer the `toml` format.

`example` folder has:
- `hugo-en` - single-language configuration file, use this if you are not going to localize your blog
- `hugo-en-ja` - two-language configuration file, more of an example of how to localize the settings as you see fit.

Choose one of the config files from `themes/neopost/example/` and copy it over to the root of your project as `hugo.toml` or `hugo.yaml`

### Parameters

About theme:

You can also add your own custom themes at `/data/custom_themes.yaml` and add its name in the `theme` parameter. if a name of a theme by neopost is conflicted with a custom theme, the themes by neopost are prioritized. all of this is showcased in the example site!

List of parameters you can set:

| Parameter | Type | Description |
|---|---|---|
| `theme` | String | Choose: `light-blue`, `dark-blue`, `light-green`, `light-yellow`, `light-pink`, `light-purple` |
| `favicon` | String | Path to the website's favicon. |
| `posts-per-page` | Integer | Number of posts displayed per page. Default: 5 |
| `toc-auto-numbering` | Boolean | Automatically number table-of-contents entries globally. |
| `dateformat` | String | The format of the time. [IMPORTANT: Please see the Golang docs on how to input the format properly.](https://pkg.go.dev/time#pkg-constants)

#### Sidebar

| Parameter | Type | Description |
|---|---|---|
| `sidebar.tags.enable` | Boolean | Enable or disable the tag list in the sidebar. |
| `sidebar.tags.limit` | Integer | Maximum number of tags displayed in the sidebar. Default 5 |
| `sidebar.tags.more-text` | String | Text displayed for the link to additional tags. |

#### Read More

| Parameter | Type | Description |
|---|---|---|
| `read-more.length-limit` | Integer | Character limit before the read-more button appears. |
| `read-more.text.more` | String | Text displayed when the content is collapsed. |
| `read-more.text.less` | String | Text displayed when the content is expanded. |

## example site
it's *HIGHLY!* recommended to test the example provided with the theme, just to learn how to mess with it. you can do that by running (considering you already did the installation steps):
```bash
cp -r themes/neopost/example/. .
hugo serve
```

In the example, you can see how to set up your hugo blog in two languages, 
and also how to arrange the images with the post so you don't need to put them all into the `static` folder.

note: images provided in this example site are mostly taken from the [library of congress](https://www.loc.gov/free-to-use/cats/).

## creating content

For the new posts, sidebar and headers, you can edit the files in the archetypes folder to change the template.

### posts
```
hugo new content/posts/new-post.md
```
this is most of your stuff, a post will appear at the main page and each one will have a page for itself. you can also attribute tags to your posts, which then can be filtered to easily find specific posts.
you can edit it at `content/posts/new-post.md`.


### sidebar
```
hugo new --kind sidebar sidebar
```
the sidebar from the main page, add a bio and little information about you!
you can edit it at the directory `content/sidebar/`, there are multiple markdown files to edit


### welcome header
```
hugo new --kind welcome-header welcome-header
```
this is above all the posts in the main page, you can give yourself a better introduction here, and say whatever you want.
you can edit it at `content/welcome-header/_index.md`.

### Publishing to Neocities

1. Generate the webpage by 

```bash
hugo
```
2. Upload the **contents of `public/`** (not the public folder itself) to the root directory of your Neocities website.

There are of course more advanced ways to do it (like when you git push to your repo, then a github action would upload it to neocities. Just search for it!)

### license
*neopost* is licensed under the [gpl-3.0 license](https://raw.githubusercontent.com/salatine/neopost/main/LICENSE).
