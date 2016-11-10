# MPAA website

The MPAA application is a Jekyll generated static website, built from JSON datafiles containing the questions,
help and information content, and page/question composition and pathways.

The website uses a ruby Generator plugin, so will not build fully on gh-pages. Must be built offline and manually uploaded to gh-pages.

# building the website:

bundle exec jekyll serve

# push _site to gh-pages branch:
ensure latest build has been committed to master branch.

git subtree push --prefix _site origin gh-pages
