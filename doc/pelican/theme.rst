Theme
#####

:breadcrumb: {filename}/pelican.rst Pelican

.. role:: rst(code)
    :language: rst

The second largest offering of ``m.css`` is a full-featured theme for the
`Pelican static site generator <https://getpelican.com/>`_. The theme is
designed to fit both the use case of a simple blog consisting of just articles
or a full product/project/portfolio website where the blog is only a side dish.

.. contents::
    :class: m-block m-default

`Quick start`_
==============

The easiest way to start is putting the :gh:`whole Git repository <mosra/m.css>`
of ``m.css`` into your project, for example as a submodule:

.. code:: sh

    git submodule add git://github.com/mosra/m.css

The most minimal configuration to use the theme is the following. Basically you
need to tell Pelican where the theme resides (it's in the ``pelican-theme/``
subdir of your ``m.css`` submodule), then you tell it to put the static
contents of the theme into a ``static/`` directory in the root of your
webserver; the ``CSS_FILES`` variable is a list of CSS files that the theme
needs. You can put there any files you need, but there need to be at least the
files mentioned on the `CSS themes <{filename}/css/themes.rst>`_ page.

.. code:: py

    THEME = 'm.css/pelican-theme'
    THEME_STATIC_DIR = 'static'
    CSS_FILES = ['https://fonts.googleapis.com/css?family=Source+Code+Pro:400,400i,600%7CSource+Sans+Pro:400,400i,600&amp;subset=latin-ext',
                 '/static/m-dark.css']
    DIRECT_TEMPLATES = ['index']

Here you can take advantage of the ``pelicanconf.py`` and ``publishconf.py``
distinction --- use ``m-dark.css`` for local development and override the
:py:`CSS_FILES` to use the smaller, faster and more compatible ``m-dark.compiled.css``
for publishing.

.. note-info::

    The above configuration should be enough to produce a (mostly empty)
    version of your website using the theme without any errors during
    processing. If that's not the case, please :gh:`report a bug <mosra/m.css/issues/new>`.
    Thank you!

`Configuration`_
================

Theme color :html:`<meta>` tag used by `CSS themes`_ can be specified with
the :py:`THEME_COLOR` variable. If not set, no theme color :html:`<meta>` tag
is present. Example configuration for the builtin dark theme:

.. code:: py

    THEME_COLOR = '#22272e'

Value of :py:`SITENAME` is used in the :html:`<title>` tag, separated with a
``|`` character from page / article name.

`Top navbar`_
-------------

:py:`SITE_LOGO` is an image file that will be used as a brand logo on left side
of the navbar, :py:`SITE_LOGO_TEXT` is brand logo text. Specifying just one of
these does the expected thing. The brand logo/text is a link that leads to
:py:`SITTEURL`.

:py:`LINKS_NAVBAR1` and :py:`LINKS_NAVBAR2` variables contain links to put in
the top navbar. On narrow screens, the navbar is divided into two columns,
links from the first variable are in the left column while links from the
second variable are in the right column. Omit the second variable if you want
the links to be in a single column.

Both variables have the same format --- a list of 4-tuples, where first item is
link title, second the URL, third page slug of the corresponding page (used
to highlight currently active menu item) and fourth is a list of sub-menu items
(which are 3-tuples --- link title, URL and page slug). Providing an empty slug
will make the menu item never highlighted; providing an empty list of sub-menu
items will not add any submenu.

Example configuration, matching example markup from the
`CSS page layout <{filename}/css/page-layout.rst#sub-menus-in-the-navbar>`__
documentation:

.. code:: py

    SITE_LOGO_TEXT = 'Your Brand'

    LINKS_NAVBAR1 = [('Features', '/features/', 'features', []),
                     ('Showcase', '/showcase/', 'showcase', []),
                     ('Download', '/download/', 'download', [])]

    LINKS_NAVBAR2 = [('Blog', '/blog/', 'blog', [
                        ('News', '/blog/news/', ''),
                        ('Archive', '/blog/archive/', '')]),
                     ('Contact', '/contact/', 'contact', [])]

`Footer navigation`_
--------------------

Similarly to the top navbar, :py:`LINKS_FOOTER1`, :py:`LINKS_FOOTER2`,
:py:`LINKS_FOOTER3` and :py:`LINKS_FOOTER4` variables contain links to put in
the footer navigation. The links are arranged in four columns, which get
reduced to just two columns on small screens. Omitting :py:`LINKS_FOOTER4` will
fill the last column with a *Blog* entry, linking to the Archives page and
listing all blog categories; omitting any of the remaining variables will make
given column empty.

The variables are lists of 2-tuples, containing link title and URL. First item
is used for column header, if link URL of the first item is empty, given column
header is just a plain :html:`<h3>` without a link.

Footer fine print can be specified via :py:`FINE_PRINT`. Contents of the
variable are processed as :abbr:`reST <reStructuredText>`, so you can use all
the formatting and linking capabilities in there.

Example configuration, again matching example markup from the
`CSS page layout <{filename}/css/page-layout.rst#footer-navigation>`__
documentation, populating the last column implicitly:

.. code:: py

    LINKS_FOOTER1 = [('Your Brand', '/'),
                     ('Features', '/features/'),
                     ('Showcase', '/showcase/')]

    LINKS_FOOTER2 = [('Download', '/download/'),
                     ('Packages', '/download/packages/'),
                     ('Source', '/download/source/')]

    LINKS_FOOTER3 = [('Contact', '/contact/'),
                     ('E-mail', '#'),
                     ('GitHub', '#')]

    FINE_PRINT = """
    Your Brand. Copyright © `You <mailto:you@your.brand>`_, 2017. All rights
    reserved.
    """

`Pages`_
========

Page content is simply put into :html:`<main>`, wrapped in an :html:`<article>`,
in the center 10 columns on large screens and spanning the full 12 columns
elsewhere. Page title is rendered in an :html:`<h1>` and there's nothing else
apart from the page content.

`Extra CSS`_
------------

The :rst:`:css:` field can be used to link additional CSS files in page header.
Put one URL per line, internal link targets are expanded. Example:

.. code:: rst

    Showcase
    ########

    :css:
        {filename}/static/webgl.css
        {filename}/static/canvas-controls.css

`Breadcrumb navigation`_
------------------------

It's common for pages to be organized in a hierarchy and the user should be
aware of it. ``m.css`` Pelican theme provides breadcrumb navigation, which is
rendered in main page heading (as described in the
`CSS page layout <{filename}/css/page-layout.rst#breadcrumb-navigation>`__
documentation) and also in page title. Breadcrumb links are taken from the
:rst:`:breadcrumb:` field, where every line is one level of hierarchy,
consisting of an internal target link (which gets properly expanded) and title
separated by whitespace.

Example usage:

.. code:: rst

    Steam engine
    ############

    :breadcrumb: {filename}/help.rst Help
                 {filename}/help/components.rst Components

.. note-info::

    You can see the breadcrumb in action on the top and bottom of this
    documentation page (and others).

`Landing pages`_
----------------

It's possible to override the default 10-column behavior for pages to make a
`landing page <{filename}/css/page-layout.rst#landing-pages>`__ with large
cover image spanning the whole window width. Put cover image URL into a
:rst:`:cover:` field, the :rst:`:landing:` field then contains
:abbr:`reST <reStructuredText>`-processed content that appears on top of the
cover image. Contents of the :rst:`:landing:` are put into a
:html:`<div class="m-container">`, you are expected to fully take care of rows
and columns in it.

.. block-warning:: Configuration

    Currently, in order to have the :rst:`:landing:` field properly parsed, you
    need to explicitly list it in :py:`FORMATTED_FIELDS`. Don't forget that
    :py:`'summary'` is already listed there.

    .. code:: py

        FORMATTED_FIELDS += ['landing']

Example of a fully custom index page that overrides the default theme index
page (which would just list all the articles) is below. Note the overriden save
destination and URL.

.. code:: rst

    Your Brand
    ##########

    :save_as: index.html
    :url:
    :cover: {filename}/static/cover.jpg
    :landing:
        .. container:: m-row

            .. container:: m-col-m-6 m-push-m-5

                .. raw:: html

                    <h1>Your Brand</h1>

                *This is the brand you need.*

.. block-warning:: Landing page title

    To give you full control over the landing page appearance, the page title
    is not rendered in :html:`<h1>` on top of the content as with usual pages.
    Instead you are expected to provide a heading inside the :rst:`:landing:`
    field. However, due to semantic restrictions of :abbr:`reST <reStructuredText>`,
    it's not possible to use section headers inside the :rst:`:landing:` field
    and you have to work around it using raw HTML blocks, as shown in the above
    example.

.. note-info::

    You can see the landing page in action on the `main project page <{filename}/index.rst>`_.

`(Social) meta tags for pages`_
-------------------------------

You can use :rst:`:description:` field to populate :html:`<meta name="description">`,
which can be then shown in search engine results. Other than that, the field
does not appear anywhere on the rendered page. For sharing pages on Twitter,
Facebook and elsewhere, both `Open Graph <http://ogp.me/>`_ and
`Twitter Card <https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/summary-card-with-large-image>`_
:html:`<meta>` tags are supported:

-   Page title is mapped to ``og:title`` / ``twitter:title``
-   Page URL is mapped to ``og:url`` / ``twitter:url``
-   The :rst:`:summary:` field is mapped to ``og:description`` /
    ``twitter:description``. Note that if the page doesn't have explicit
    summary, Pelican takes it from the first few sentences of the content and
    that may not be what you want. This is also different from the
    :rst:`:description:` field mentioned above and, unlike with articles,
    :rst:`:summary:` doesn't appear anywhere on the rendered page.
-   The :rst:`:cover:` field (e.g. the one used on `landing pages <#landing-pages>`_),
    if present, is mapped to ``og:image`` / ``twitter:image``. The exact same
    file is used without any resizing or cropping and is assumed to be in
    landscape.
-   ``twitter:card`` is set to ``summary_large_image`` if :rst:`:cover:` is
    present and to ``summary`` otherwise
-   ``og:type`` is set to ``website``

Example overriding the index page with essential properties for nice-looking
social links:

.. code:: rst

    Your Brand
    ##########

    :save_as: index.html
    :url:
    :cover: {filename}/static/cover.jpg
    :summary: This is the brand you need.

.. note-success::

    You can see how page links will display by pasting
    URL of the `index page <{filename}/index.rst>`_ into either
    `Facebook Debugger <https://developers.facebook.com/tools/debug/>`_ or
    `Twitter Card Validator <https://cards-dev.twitter.com/validator>`_.

`Articles`_
===========

`Jumbo articles`_
-----------------

`Jumbo articles <{filename}/css/page-layout.rst#jumbo-articles>`__ are made
by including the :rst:`:cover:` field containing URL of the cover image.
Besides that, if the title contains an em-dash (---), it gets split into a
title and subtitle that's then rendered in a different font size. Example:

.. code:: rst

    An Article --- a jumbo one
    ##########################

    :cover: {filename}/static/ship.jpg
    :slug: jumbo-article
    :summary: Article summary paragraph.

.. note-info::

    You can compare how an article with nearly the same contents looks as
    `a normal article <{filename}/examples/article.rst>`_ and a
    `jumbo article <{filename}/examples/jumbo-article.rst>`_.

`(Social) meta tags for articles`_
----------------------------------

Like with pages, you can use :rst:`:description:` field to populate
:html:`<meta name="description">`, which can be then shown in search engine
results. Other than that, the field doesn't appear anywhere in the rendered
article. `Open Graph`_ and `Twitter Card`_ :html:`<meta>` tags are also
supported in a similar way:

-   Article title is mapped to ``og:title`` / ``twitter:title``
-   Pernament article URL is mapped to ``og:url`` / ``twitter:url``
-   The :rst:`:summary:` field is mapped to ``og:description`` /
    ``twitter:description``. Note that if the article doesn't have explicit
    summary, Pelican takes it from the first few sentences of the content and
    that may not be what you want. This is also different from the
    :rst:`:description:` field mentioned above.
-   The :rst:`:cover:` field from `jumbo articles <#jumbo-articles>`_, if
    present, is mapped to ``og:image`` / ``twitter:image``. The exact same
    file is used without any resizing or cropping and is assumed to be in
    landscape.
-   ``twitter:card`` is set to ``summary_large_image`` if :rst:`:cover:` is
    present and to ``summary`` otherwise
-   ``og:type`` is set to ``article``

.. note-success::

    You can see how article links will display by pasting
    URL of e.g. the `jumbo article`_ into either `Facebook Debugger`_ or
    `Twitter Card Validator`_.

`Pre-defined pages`_
====================

With the default configuration above the index page is just a list of articles
with the first being expanded, the same is for the archives page. If you want
to have a custom index page (for example a `landing page <#landing-pages>`_),
remove :py:`'index'` from the :py:`DIRECT_TEMPLATES` setting:

.. code:: py

    DIRECT_TEMPLATES = []

Every category, tag and author has its own page that lists corresponding
articles in a way similar to the index or archives page, but without the first
article expanded. On the top of the page there is a note stating what condition
the articles are filtered with.

.. note-info::

    See how an example `category page looks <{category}Examples>`_.

Index, archive and all category/tag/author pages are paginated based on the
:py:`DEFAULT_PAGINATION` setting --- on the bottom of each page there are link
to prev and next page, besides that there's :html:`<link rel="prev">` and
:html:`<link rel="next">` that provides the same as a hint to search engines.

.. note-warning::

    The ``m.css`` Pelican theme doesn't provide per-year, per-month or per-day
    archive pages or category, tag, author *list* pages at the moment. List of
    categories and tags is available in a sidebar from any article or article
    listing page.

`Theme properties`_
===================

The theme markup is designed to have readable, nicely indented output. The code
is valid HTML5 and should be parsable as XML.

.. note-danger::

    This is one of the main goals of this project. Please
    :gh:`report a bug <mosra/m.css/issues/new>` if it's not like that.

.. note-dim::
    :class: m-text-center

    `« Writing content <{filename}/pelican/writing-content.rst>`_ | `Pelican <{filename}/pelican.rst>`_