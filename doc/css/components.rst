..
    This file is part of m.css.

    Copyright © 2017 Vladimír Vondruš <mosra@centrum.cz>

    Permission is hereby granted, free of charge, to any person obtaining a
    copy of this software and associated documentation files (the "Software"),
    to deal in the Software without restriction, including without limitation
    the rights to use, copy, modify, merge, publish, distribute, sublicense,
    and/or sell copies of the Software, and to permit persons to whom the
    Software is furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included
    in all copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL
    THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
    FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
    DEALINGS IN THE SOFTWARE.
..

Components
##########

:breadcrumb: {filename}/css.rst CSS
:footer:
    .. note-dim::
        :class: m-text-center

        `« Typography <{filename}/css/typography.rst>`_ | `CSS <{filename}/css.rst>`_ | `Page layout » <{filename}/css/page-layout.rst>`_

m.css provides a set of basic components for further improving the layout and
display of authored content.

.. contents::
    :class: m-block m-default

`Colors`_
=========

Similarly to Bootstrap, m.css has a set of predefined colors that affect how a
certain component looks. This works on majority of components shown on this
page. The colors are:

-   :css:`.m-default` is a default style that doesn't grab attention
-   :css:`.m-primary` is meant to be used to highlight the primary element on a
    page
-   :css:`.m-success` is good to highlight happy things
-   :css:`.m-warning` catches attention, but doesn't hurt
-   :css:`.m-danger` brings really bad news
-   :css:`.m-info` is for side notes
-   :css:`.m-dim` is shy and doesn't want you to be bothered by the information
    it brings

`Blocks`_
=========

Blocks, defined by :css:`.m-block`, wrap the content in a light frame and add a
bolder colored bar on the left. Use in combination with one of the color styles
above. Block caption should go into :html:`<h3>` and is colored in respect to
the color style as well. Text and links always have the default color, except
for :css:`.m-block.m-dim`. It's also possible to have a block without the
border, just add :css:`.m-flat` class to it.

.. code-figure::

    .. code:: html

        <div class="m-block m-default">
          <h3>Default block</h3>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices
          a erat eu suscipit. <a href="#">Link.</a>
        </div>

    .. raw:: html

        <div class="m-row">
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-block m-default">
              <h3>Default block</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. <a href="#">Link.</a>
            </div>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-block m-primary">
              <h3>Primary block</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. <a href="#">Link.</a>
            </div>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-block m-success">
              <h3>Success block</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. <a href="#">Link.</a>
            </div>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-block m-warning">
              <h3>Warning block</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. <a href="#">Link.</a>
            </div>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-block m-danger">
              <h3>Danger block</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. <a href="#">Link.</a>
            </div>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-block m-info">
              <h3>Info block</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. <a href="#">Link.</a>
            </div>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-block m-dim">
              <h3>Dim block</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. <a href="#">Link.</a>
            </div>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-block m-flat">
              <h3>Flat block</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. <a href="#">Link.</a>
            </div>
          </div>
        </div>

`Notes, frame`_
===============

Unlike blocks, notes are meant to wrap smaller bits of information. Use the
:css:`.m-note` CSS class together with desired color class. A note is also
slightly rounded and has everything colored, the background, the caption, text
and also links. The :html:`<h3>` caption tag is optional.

Besides notes, there is a frame element defined by :css:`.m-frame`, which just
wraps your content in a slightly rounded border. No color classes apply to a
frame.

.. code-figure::

    .. code:: html

        <div class="m-note m-success">
          <h3>Success note</h3>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. <a href="#">Link.</a>
        </div>

    .. raw:: html

        <div class="m-row">
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-note m-default">
              <h3>Default note</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. <a href="#">Link.</a>
            </div>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-note m-primary">
              <h3>Primary note</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. <a href="#">Link.</a>
            </div>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-note m-success">
              <h3>Success note</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. <a href="#">Link.</a>
            </div>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-note m-warning">
              <h3>Warning note</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. <a href="#">Link.</a>
            </div>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-note m-danger">
              <h3>Danger note</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. <a href="#">Link.</a>
            </div>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-note m-info">
              <h3>Info note</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. <a href="#">Link.</a>
            </div>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-note m-dim">
              <h3>Dim note</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. <a href="#">Link.</a>
            </div>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <div class="m-frame">
              <h3>Frame</h3>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. <a href="#">Link.</a>
            </div>
          </div>
        </div>

`Text`_
=======

Use :css:`.m-text` CSS class together with desired color class to color a
paragraph or inline text.

.. code-figure::

    .. code:: html

        <p class="m-text m-warning">Warning text. Lorem ipsum dolor sit amet,
        consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. Aliquam
        pharetra imperdiet tortor sed vehicula. <a href="#">Link.</a></p>

    .. raw:: html

        <div class="m-row">
          <div class="m-col-m-3 m-col-s-6">
            <p class="m-text m-default m-noindent">Default text. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. Aliquam pharetra imperdiet tortor sed vehicula. <a href="#">Link.</a></p>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <p class="m-text m-primary m-noindent">Primary text. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. Aliquam pharetra imperdiet tortor sed vehicula. <a href="#">Link.</a></p>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <p class="m-text m-success m-noindent">Success text. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. Aliquam pharetra imperdiet tortor sed vehicula. <a href="#">Link.</a></p>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <p class="m-text m-warning m-noindent">Warning text. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. Aliquam pharetra imperdiet tortor sed vehicula. <a href="#">Link.</a></p>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <p class="m-text m-danger m-noindent">Danger text. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. Aliquam pharetra imperdiet tortor sed vehicula. <a href="#">Link.</a></p>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <p class="m-text m-info m-noindent">Info text. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. Aliquam pharetra imperdiet tortor sed vehicula. <a href="#">Link.</a></p>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <p class="m-text m-dim m-noindent">Dim text. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ultrices a erat eu suscipit. Aliquam pharetra imperdiet tortor sed vehicula. <a href="#">Link.</a></p>
          </div>
        </div>

Apply :css:`.m-small` or :css:`.m-big` CSS class together with :css:`.m-text`
to make the text appear smaller or larger.

.. code-figure::

    .. code:: html

        <p class="m-text m-big">Larger text. Lorem ipsum dolor sit amet, consectetur
        adipiscing elit. Vivamus ultrices a erat eu suscipit. Aliquam pharetra
        imperdiet tortor sed vehicula.</p>
        <p class="m-text m-small">Smaller text. Lorem ipsum dolor sit amet, consectetur
        adipiscing elit. Vivamus ultrices a erat eu suscipit. Aliquam pharetra
        imperdiet tortor sed vehicula.</p>

    .. raw:: html

        <p class="m-text m-big">Larger text. Lorem ipsum dolor sit amet, consectetur
        adipiscing elit. Vivamus ultrices a erat eu suscipit. Aliquam pharetra
        imperdiet tortor sed vehicula.</p>
        <p class="m-text m-small">Smaller text. Lorem ipsum dolor sit amet, consectetur
        adipiscing elit. Vivamus ultrices a erat eu suscipit. Aliquam pharetra
        imperdiet tortor sed vehicula.</p>

Besides :html:`<strong>` and :html:`<em>` you can use :css:`.m-strong` or
:css:`.m-em` CSS class together with :css:`.m-text` to achieve the same effect
without using those particular tags.

.. code-figure::

    .. code:: html

        <p>Lorem ipsum dolor sit amet; <span class="m-text m-strong">strong text</span>;
        consectetur adipiscing elit. <span class="m-text m-em">Emphasised.</span></p>

    .. raw:: html

        <p>Lorem ipsum dolor sit amet; <span class="m-text m-strong">strong text</span>;
        consectetur adipiscing elit. <span class="m-text m-em">Emphasised.</span></p>

`Button links`_
===============

To highlight important links such as file download, you can style them as
buttons. Use :css:`.m-button` CSS class together with desired color class on an
:html:`<a>` tag. The button is by default displayed as inline block, either
wrap it in :css:`.m-text-center` etc. :html:`<div>` to make it centered or
apply a :css:`.m-fullwidth` class to it to display it as a full-width block
with center-aligned label.

.. code-figure::

    .. code:: html

        <a class="m-button m-success" href="#">Success button</a>

    .. raw:: html

        <div class="m-row">
          <div class="m-col-m-3 m-col-s-6">
            <a class="m-button m-default m-fullwidth" href="#">Default button</a>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <a class="m-button m-primary m-fullwidth" href="#">Primary button</a>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <a class="m-button m-success m-fullwidth" href="#">Success button</a>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <a class="m-button m-warning m-fullwidth" href="#">Warning button</a>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <a class="m-button m-danger m-fullwidth" href="#">Danger button</a>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <a class="m-button m-info m-fullwidth" href="#">Info button</a>
          </div>
          <div class="m-col-m-3 m-col-s-6">
            <a class="m-button m-dim m-fullwidth" href="#">Dim button</a>
          </div>
        </div>

You can put two :html:`<div>`\ s with :css:`.m-big` and :css:`.m-small` CSS
class inside the :html:`<a>` to achieve the following effect:

.. code-figure::

    .. code:: html

        <div class="m-text-center">
          <a class="m-button m-primary" href="#">
            <div class="m-big">Download the thing</div>
            <div class="m-small">Any platform, 5 kB.</div>
          </a>
        </div>

    .. raw:: html

        <div class="m-text-center">
          <a class="m-button m-primary" href="#">
            <div class="m-big">Download the thing</div>
            <div class="m-small">Any platform, 5 kB.</div>
          </a>
        </div>

`Tables`_
=========

Use :css:`.m-table` to apply styling to a table. The table is centered by
default; rows are separated by lines, with :html:`<thead>` and :html:`<tfoot>`
being separated by a thicker line. Rows are highlighted on hover, :html:`<th>`
is rendered in bold, all :html:`<th>` and :html:`<td>` are aligned to left
while table :html:`<caption>` is centered. Example table:

.. code-figure::

    .. code:: html

        <table class="m-table">
          <caption>Table caption</caption>
          <thead>
            <tr>
              <th>#</th>
              <th>Heading</th>
              <th>Second<br/>heading</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <th scope="row">1</th>
              <td>Cell</td>
              <td>Second cell</td>
            </tr>
          </tbody>
          <tbody>
            <tr>
              <th scope="row">2</th>
              <td>2nd row cell</td>
              <td>2nd row 2nd cell</td>
            </tr>
          </tbody>
          <tfoot>
            <tr>
              <th>&Sigma;</th>
              <td>Footer</td>
              <td>Second<br/>footer</td>
            </tr>
          </tfoot>
        </table>

    .. raw:: html

        <table class="m-table">
          <caption>Table caption</caption>
          <thead>
            <tr>
              <th>#</th>
              <th>Heading</th>
              <th>Second<br/>heading</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <th scope="row">1</th>
              <td>Cell</td>
              <td>Second cell</td>
            </tr>
          </tbody>
          <tbody>
            <tr>
              <th scope="row">2</th>
              <td>2nd row cell</td>
              <td>2nd row 2nd cell</td>
            </tr>
          </tbody>
          <tfoot>
            <tr>
              <th>&Sigma;</th>
              <td>Footer</td>
              <td>Second<br/>footer</td>
            </tr>
          </tfoot>
        </table>

Similarly to other components, you can color particular :html:`<tr>` or
:html:`<td>` elements using the color classes from above:

.. raw:: html

    <div class="m-scroll"><table class="m-table m-fullwidth">
      <tbody>
        <tr class="m-default">
          <td>Default row</td>
          <td>Lorem</td>
          <td>ipsum</td>
          <td>dolor</td>
          <td>sit</td>
          <td>amet</td>
          <td><a href="#">Link</a></td>
        </tr>
        <tr class="m-primary">
          <td>Primary row</td>
          <td>Lorem</td>
          <td>ipsum</td>
          <td>dolor</td>
          <td>sit</td>
          <td>amet</td>
          <td><a href="#">Link</a></td>
        </tr>
        <tr class="m-success">
          <td>Success row</td>
          <td>Lorem</td>
          <td>ipsum</td>
          <td>dolor</td>
          <td>sit</td>
          <td>amet</td>
          <td><a href="#">Link</a></td>
        </tr>
        <tr class="m-warning">
          <td>Warning row</td>
          <td>Lorem</td>
          <td>ipsum</td>
          <td>dolor</td>
          <td>sit</td>
          <td>amet</td>
          <td><a href="#">Link</a></td>
        </tr>
        <tr class="m-danger">
          <td>Danger row</td>
          <td>Lorem</td>
          <td>ipsum</td>
          <td>dolor</td>
          <td>sit</td>
          <td>amet</td>
          <td><a href="#">Link</a></td>
        </tr>
        <tr class="m-info">
          <td>Info row</td>
          <td>Lorem</td>
          <td>ipsum</td>
          <td>dolor</td>
          <td>sit</td>
          <td>amet</td>
          <td><a href="#">Link</a></td>
        </tr>
        <tr class="m-dim">
          <td>Dim row</td>
          <td>Lorem</td>
          <td>ipsum</td>
          <td>dolor</td>
          <td>sit</td>
          <td>amet</td>
          <td><a href="#">Link</a></td>
        </tr>
      </tbody>
    </table></div>

`Images`_
=========

Putting :css:`.m-image` class onto the :html:`<img>` tag makes it centered,
slightly rounded and sets its max width to 100%. Adding :css:`.m-fullwidth` on
the image element works as expected. For accessibility reasons it's a good
practice to include the ``alt`` attribute.

.. code-figure::

    .. code:: html

        <img src="flowers.jpg" alt="Flowers" class="m-image" />

    .. raw:: html

        <img src="{filename}/static/flowers-small.jpg" alt="Flowers" class="m-image" />

To make the image clickable, wrap the :html:`<a>` tag in an additional
:html:`<div>` and put the :css:`.m-image` class on the :html:`<div>` element
instead of on the image. This will ensure that only the image is clickable and
not the surrounding area:

.. code-figure::

    .. code:: html

        <div class="m-image">
          <a href="flowers.jpg"><img src="flowers.jpg" /></a>
        </div>

    .. raw:: html

        <div class="m-image">
          <a href="{filename}/static/flowers.jpg"><img src="{filename}/static/flowers-small.jpg" /></a>
        </div>

`Figures`_
==========

Use the HTML5 :html:`<figure>` tag together with :css:`.m-figure` to style it.
As with plain image, it's by default centered, slightly rounded and has a
border around the caption and description. The caption is expected to be in the
:html:`<figcaption>` element. The description is optional, but should be
wrapped in some tag as well (for example a :html:`<span>`). The
:css:`.m-fullwidth` class works here too and you can also wrap the
:html:`<img>` element in an :html:`<a>` tag to make it clickable.

Figure always expects at least the caption to be present. If you want just an
image, use the plain image tag. If you have a lot of figures on the page and
the border is distracting, apply the :css:`.m-flat` class to hide it.

.. code-figure::

    .. code:: html

        <figure class="m-figure">
          <img src="ship.jpg" alt="Ship" />
          <figcaption>A Ship</figcaption>
          <span>Photo © <a href="http://blog.mosra.cz/">The Author</a></span>
        </figure>

    .. raw:: html

        <figure class="m-figure">
          <img src="{filename}/static/ship-small.jpg" alt="Ship" />
          <figcaption>A Ship</figcaption>
          <span>Photo © <a href="http://blog.mosra.cz/">The Author</a></span>
        </figure>

`Image grid`_
=============

Inspired by `image grids on Medium <https://blog.medium.com/introducing-image-grids-c592e5bc16d8>`_,
its purpose is to present photos in a beautiful way. Wrap one or more
:html:`<figure>` elements in a :html:`<div class="m-imagegrid">` element and
delimit each row with a wrapper :html:`<div>`. Each :html:`<figure>` element
needs to contain an :html:`<img>` and a :html:`<figcaption>` with image caption
that appears on hover; these two elements can be optionally wrapped in an
:html:`<a>` to make the image clickable. If you don't want a caption, use an
empty :html:`<div>` instead of :html:`<figcaption>`. If you want the grid to
`inflate to full container width <{filename}/css/grid.rst#inflatable-nested-grid>`_,
add a :css:`.m-container-inflate` CSS class to it.

.. note-warning::

    The inner :html:`<div>` or :html:`<figcaption>` element is *important*,
    without it the grid won't look as desired.

Example usage (stupidly showing the two images all over again --- sorry):

.. code:: html

    <div class="m-imagegrid m-container-inflate">
      <div>
        <figure style="width: 69.127%">
          <a href="ship.jpg">
            <img src="ship.jpg" />
            <figcaption>F9.0, 1/250 s, ISO 100</figcaption>
          </a>
        </figure>
        <figure style="width: 30.873%">
          <a href="flowers.jpg">
            <img src="flowers.jpg" />
            <figcaption>F2.8, 1/1600 s, ISO 100</figcaption>
          </a>
        </figure>
      </div>
      <div>
        <figure style="width: 30.873%">
          <a href="flowers.jpg">
            <img src="flowers.jpg" />
            <figcaption>F2.8, 1/1600 s, ISO 100</figcaption>
          </a>
        </figure>
        <figure style="width: 69.127%">
          <a href="ship.jpg">
            <img src="ship.jpg" />
            <figcaption>F9.0, 1/250 s, ISO 100</figcaption>
          </a>
        </figure>
      </div>
    </div>

.. raw:: html

    <div class="m-imagegrid m-container-inflate">
      <div>
        <figure style="width: 69.127%">
          <a href="{filename}/static/ship.jpg">
            <img src="{filename}/static/ship.jpg" />
            <figcaption>F9.0, 1/250 s, ISO 100</figcaption>
          </a>
        </figure>
        <figure style="width: 30.873%">
          <a href="{filename}/static/flowers.jpg">
            <img src="{filename}/static/flowers.jpg" />
            <figcaption>F2.8, 1/1600 s, ISO 100</figcaption>
          </a>
        </figure>
      </div>
      <div>
        <figure style="width: 30.873%">
          <a href="{filename}/static/flowers.jpg">
            <img src="{filename}/static/flowers.jpg" />
            <figcaption>F2.8, 1/1600 s, ISO 100</figcaption>
          </a>
        </figure>
        <figure style="width: 69.127%">
          <a href="{filename}/static/ship.jpg">
            <img src="{filename}/static/ship.jpg" />
            <figcaption>F9.0, 1/250 s, ISO 100</figcaption>
          </a>
        </figure>
      </div>
    </div>

The core idea behind the image grid is scaling particular images to occupy the
same height on given row. First, a sum :math:`W` of image aspect ratios is
calculated for the whole row:

.. math::

    W = \sum_{i=0}^{n-1} \cfrac{w_i}{h_i}

Then, percentage width :math:`p_i` of each image is calculated as:

.. math::

    p_i = W \cfrac{w_i}{h_i} \cdot 100 \%

.. note-info::

    The image width calculation is quite annoying to do manually, that's why
    m.css provides a `Pelican plugin <{filename}/plugins/images.rst#image-grid>`_
    that does the hard work for you.

`Code`_
=======

m.css recognizes code highlighting compatible with `Pygments <http://pygments.org/>`_
and provides additional styling for it. There's a set of builtin `pygments-*.css <{filename}/css.rst>`_
styles that match the m.css themes.

For example, code highlighted using:

.. code:: sh

    echo -e "int main() {\n    return 0;\n}" | pygmentize -f html -l c++ -O nowrap

Will spit out a bunch of :html:`<span>` elements like below. To create a code
block, wrap the output in :html:`<pre class="m-code">` (note that whitespace
matters inside this tag). The block doesn't wrap lines on narrow screens to not
hurt readability, a horizontal scrollbar is shown instead if the content is
too wide.

.. code-figure::

    .. code:: html

        <pre class="m-code"><span class="kt">int</span> <span class="nf">main</span><span class="p">()</span> <span class="p">{</span>
            <span class="k">return</span> <span class="mi">0</span><span class="p">;</span>
        <span class="p">}</span></pre>

    .. raw:: html

        <pre class="m-code"><span class="kt">int</span> <span class="nf">main</span><span class="p">()</span> <span class="p">{</span>
            <span class="k">return</span> <span class="mi">0</span><span class="p">;</span>
        <span class="p">}</span></pre>

Pygments allow to highlight arbitrary lines, which affect the rendering in this
way:

.. code:: c++
    :hl_lines: 2 3

    int main() {
        std::cout << "Hello world!" << std::endl;
        return 0;
    }

Sometimes you want to focus on code that has been changed / added and mute the
rest. Add an additional :css:`.m-inverted` CSS class to the
:html:`<pre class="m-code">` to achieve this effect:

.. code:: c++
    :hl_lines: 4 5
    :class: m-inverted

    #include <iostream>

    int main() {
        std::cout << "Hello world!" << std::endl;
        return 0;
    }

To have code highlighting inline, wrap the output in :html:`<code class="m-code">`
instead of :html:`<pre>`:

.. code-figure::

    .. code:: html

        <p>The <code class="m-code"><span class="n">main</span><span class="p">()</span></code>
        function doesn't need to have a <code class="m-code"><span class="k">return</span></code>
        statement.</p>

    .. raw:: html

        <p>The <code class="m-code"><span class="n">main</span><span class="p">()</span></code>
        function doesn't need to have a <code class="m-code"><span class="k">return</span></code>
        statement.</p>

.. note-success::

    To make your life easier, m.css provides a
    `Pelican plugin <{filename}/plugins/math-and-code.rst#code>`__
    that integrates Pygments code highlighting as a :abbr:`reST <reStructuredText>`
    directive.

`Code figure`_
==============

It often happens that you want to present code with corresponding result
together. The code figure looks similar to `image figures <#figures>`_ and
consists of a :html:`<figure class="m-code-figure">` element containing a
:html:`<pre>` block and whatever else you want to put in as the result. The
:html:`<pre>` element has to be the very first child of the :html:`<figure>`
for the markup to work correctly. Similar to image figure, you can apply the
:css:`.m-flat` CSS class to remove the border.

Example (note that this page uses code figure for all code examples, so it's a
bit of a figure inception shown here):

.. code-figure::

    .. code:: html

        <figure class="m-code-figure">
          <pre>Some
            code
        snippet</pre>
          And a resulting output.
        </figure>

    .. raw:: html

        <figure class="m-code-figure">
          <pre>Some
            code
        snippet</pre>
          And a resulting output.
        </figure>

`Math`_
=======

The ``latex2svg.py`` utility from :gh:`tuxu/latex2svg` can be used to generate
SVG representation of your LaTeX math formulas. Assuming you have some LaTeX
distribution and `dvisvgm <http://dvisvgm.bplaced.net/>`_ installed, the usage
is simple:

.. code:: sh

    echo "$$ a^2 = b^2 + c^2 $$" | python pelican-plugins/latex2svg.py > formula.svg

The ``formula.svg`` file will then contain the rendered formula, which with
some minor patching (removing the XML preamble etc.) can be pasted directly
into your HTML code. The :html:`<svg>` element containing math can be wrapped
in :html:`<div class="m-math">` to make it centered. Similarly to code
blocks, the math block shows a horizontal scrollbar if the content is too wide
on narrow screens. `CSS color classes <#colors>`_ can be applied to the
:html:`<div>`. It's a good practice to include :html:`<title>` and
:html:`<desc>` elements for accessibility reasons.

.. code-figure::

    .. code:: html

        <div class="m-math m-success">
          <svg>
            <title>LaTeX Math</title>
            <desc>a^2 = b^2 + c^2</desc>
            <g>...</g>
          </svg>
        </div>

    .. raw:: html

        <div class="m-math m-success">
          <svg height='13.7321pt' version='1.1' viewBox='164.011 -10.9857 60.0231 10.9857' width='75.0289pt'>
            <title>LaTeX Math</title>
            <desc>a^2 = b^2 + c^2</desc>
            <defs>
              <path d='M3.59851 -1.42267C3.53873 -1.21943 3.53873 -1.19552 3.37136 -0.968369C3.10834 -0.633624 2.58232 -0.119552 2.02042 -0.119552C1.53026 -0.119552 1.25529 -0.561893 1.25529 -1.26725C1.25529 -1.92478 1.6259 -3.26376 1.85305 -3.76588C2.25953 -4.60274 2.82142 -5.03313 3.28767 -5.03313C4.07671 -5.03313 4.23213 -4.0528 4.23213 -3.95716C4.23213 -3.94521 4.19626 -3.78979 4.18431 -3.76588L3.59851 -1.42267ZM4.36364 -4.48319C4.23213 -4.79402 3.90934 -5.27223 3.28767 -5.27223C1.93674 -5.27223 0.478207 -3.52677 0.478207 -1.75741C0.478207 -0.573848 1.17161 0.119552 1.98456 0.119552C2.64209 0.119552 3.20399 -0.394521 3.53873 -0.789041C3.65828 -0.0836862 4.22017 0.119552 4.57883 0.119552S5.22441 -0.0956413 5.4396 -0.526027C5.63088 -0.932503 5.79826 -1.66177 5.79826 -1.70959C5.79826 -1.76936 5.75044 -1.81719 5.6787 -1.81719C5.57111 -1.81719 5.55915 -1.75741 5.51133 -1.57808C5.332 -0.872727 5.10486 -0.119552 4.61469 -0.119552C4.268 -0.119552 4.24408 -0.430386 4.24408 -0.669489C4.24408 -0.944458 4.27995 -1.07597 4.38755 -1.54222C4.47123 -1.8411 4.53101 -2.10411 4.62665 -2.45081C5.06899 -4.24408 5.17659 -4.67447 5.17659 -4.7462C5.17659 -4.91357 5.04508 -5.04508 4.86575 -5.04508C4.48319 -5.04508 4.38755 -4.62665 4.36364 -4.48319Z' id='math1-g0-97'/>
              <path d='M2.76164 -7.99801C2.7736 -8.04583 2.79751 -8.11756 2.79751 -8.17733C2.79751 -8.29689 2.67796 -8.29689 2.65405 -8.29689C2.64209 -8.29689 2.21171 -8.26102 1.99651 -8.23711C1.79328 -8.22516 1.61395 -8.20125 1.39875 -8.18929C1.11183 -8.16538 1.02814 -8.15342 1.02814 -7.93823C1.02814 -7.81868 1.1477 -7.81868 1.26725 -7.81868C1.87696 -7.81868 1.87696 -7.71108 1.87696 -7.59153C1.87696 -7.50785 1.78132 -7.16115 1.7335 -6.94595L1.44658 -5.79826C1.32702 -5.32005 0.645579 -2.60623 0.597758 -2.39103C0.537983 -2.09215 0.537983 -1.88892 0.537983 -1.7335C0.537983 -0.514072 1.21943 0.119552 1.99651 0.119552C3.38331 0.119552 4.81793 -1.66177 4.81793 -3.39527C4.81793 -4.49514 4.19626 -5.27223 3.29963 -5.27223C2.67796 -5.27223 2.11606 -4.75816 1.88892 -4.51905L2.76164 -7.99801ZM2.00847 -0.119552C1.6259 -0.119552 1.20747 -0.406476 1.20747 -1.33898C1.20747 -1.7335 1.24334 -1.96065 1.45853 -2.79751C1.4944 -2.95293 1.68568 -3.71806 1.7335 -3.87347C1.75741 -3.96912 2.46276 -5.03313 3.27572 -5.03313C3.80174 -5.03313 4.04085 -4.5071 4.04085 -3.88543C4.04085 -3.31158 3.7061 -1.96065 3.40722 -1.33898C3.10834 -0.6934 2.55841 -0.119552 2.00847 -0.119552Z' id='math1-g0-98'/>
              <path d='M4.67447 -4.49514C4.44732 -4.49514 4.33973 -4.49514 4.17235 -4.35168C4.10062 -4.29191 3.96912 -4.11258 3.96912 -3.9213C3.96912 -3.68219 4.14844 -3.53873 4.37559 -3.53873C4.66252 -3.53873 4.98531 -3.77783 4.98531 -4.25604C4.98531 -4.82989 4.43537 -5.27223 3.61046 -5.27223C2.04433 -5.27223 0.478207 -3.56264 0.478207 -1.86501C0.478207 -0.824907 1.12379 0.119552 2.34321 0.119552C3.96912 0.119552 4.99726 -1.1477 4.99726 -1.30311C4.99726 -1.37484 4.92553 -1.43462 4.87771 -1.43462C4.84184 -1.43462 4.82989 -1.42267 4.72229 -1.31507C3.95716 -0.298879 2.82142 -0.119552 2.36712 -0.119552C1.54222 -0.119552 1.2792 -0.836862 1.2792 -1.43462C1.2792 -1.85305 1.48244 -3.0127 1.91283 -3.82565C2.22366 -4.38755 2.86924 -5.03313 3.62242 -5.03313C3.77783 -5.03313 4.43537 -5.00922 4.67447 -4.49514Z' id='math1-g0-99'/>
              <path d='M4.77011 -2.76164H8.06974C8.23711 -2.76164 8.4523 -2.76164 8.4523 -2.97684C8.4523 -3.20399 8.24907 -3.20399 8.06974 -3.20399H4.77011V-6.50361C4.77011 -6.67098 4.77011 -6.88618 4.55492 -6.88618C4.32777 -6.88618 4.32777 -6.68294 4.32777 -6.50361V-3.20399H1.02814C0.860772 -3.20399 0.645579 -3.20399 0.645579 -2.98879C0.645579 -2.76164 0.848817 -2.76164 1.02814 -2.76164H4.32777V0.537983C4.32777 0.705355 4.32777 0.920548 4.54296 0.920548C4.77011 0.920548 4.77011 0.71731 4.77011 0.537983V-2.76164Z' id='math1-g2-43'/>
              <path d='M8.06974 -3.87347C8.23711 -3.87347 8.4523 -3.87347 8.4523 -4.08867C8.4523 -4.31582 8.24907 -4.31582 8.06974 -4.31582H1.02814C0.860772 -4.31582 0.645579 -4.31582 0.645579 -4.10062C0.645579 -3.87347 0.848817 -3.87347 1.02814 -3.87347H8.06974ZM8.06974 -1.64981C8.23711 -1.64981 8.4523 -1.64981 8.4523 -1.86501C8.4523 -2.09215 8.24907 -2.09215 8.06974 -2.09215H1.02814C0.860772 -2.09215 0.645579 -2.09215 0.645579 -1.87696C0.645579 -1.64981 0.848817 -1.64981 1.02814 -1.64981H8.06974Z' id='math1-g2-61'/>
              <path d='M2.24757 -1.6259C2.37509 -1.74545 2.70984 -2.00847 2.83736 -2.12005C3.33151 -2.57435 3.80174 -3.0127 3.80174 -3.73798C3.80174 -4.68643 3.00473 -5.30012 2.00847 -5.30012C1.05205 -5.30012 0.422416 -4.57484 0.422416 -3.8655C0.422416 -3.47497 0.73325 -3.41918 0.844832 -3.41918C1.0122 -3.41918 1.25928 -3.53873 1.25928 -3.84159C1.25928 -4.25604 0.860772 -4.25604 0.765131 -4.25604C0.996264 -4.83786 1.53026 -5.03711 1.9208 -5.03711C2.66202 -5.03711 3.04458 -4.40747 3.04458 -3.73798C3.04458 -2.90909 2.46276 -2.30336 1.52229 -1.33898L0.518057 -0.302864C0.422416 -0.215193 0.422416 -0.199253 0.422416 0H3.57061L3.80174 -1.42665H3.55467C3.53076 -1.26725 3.467 -0.868742 3.37136 -0.71731C3.32354 -0.653549 2.71781 -0.653549 2.59029 -0.653549H1.17161L2.24757 -1.6259Z' id='math1-g1-50'/>
            </defs>
            <g id='math1-page1'>
              <use x='164.011' xlink:href='#math1-g0-97' y='-0.913201'/>
              <use x='170.156' xlink:href='#math1-g1-50' y='-5.84939'/>
              <use x='178.209' xlink:href='#math1-g2-61' y='-0.913201'/>
              <use x='190.634' xlink:href='#math1-g0-98' y='-0.913201'/>
              <use x='195.612' xlink:href='#math1-g1-50' y='-5.84939'/>
              <use x='203.001' xlink:href='#math1-g2-43' y='-0.913201'/>
              <use x='214.762' xlink:href='#math1-g0-99' y='-0.913201'/>
              <use x='219.8' xlink:href='#math1-g1-50' y='-5.84939'/>
            </g>
          </svg>
        </div>

For inline math, add the :css:`.m-math` class to the :html:`<svg>` tag
directly. Note that you'll probably need to manually specify
:css:`vertical-align` style to make the formula align well with surrounding
text. You can use CSS color classes here as well. When using the ``latex2svg.py``
utility, wrap the formula in ``$`` instead of ``$$`` to produce inline math;
the ``depth`` value returned on stderr can be taken as a base for the
:css:`vertical-align` property.

.. code-figure::

    .. code:: html

        <p>There is <a href="https://tauday.com/">a movement</a> for replacing circle
        constant <svg class="m-math" style="vertical-align: 0.0pt">...</svg> with the
        <svg class="m-math m-warning" style="vertical-align: 0.0pt">...</svg> character.

    .. raw:: html

        <p>There is <a href="https://tauday.com/">a movement</a> for replacing
        circle constant <svg class="m-math" style="vertical-align: -0.0pt;" height='9.63055pt' version='1.1' viewBox='0 -7.70444 12.9223 7.70444' width='16.1528pt'>
          <title>LaTeX Math</title>
          <desc>2 \pi</desc>
          <defs>
            <path d='M3.09639 -4.5071H4.44732C4.12453 -3.16812 3.9213 -2.29539 3.9213 -1.33898C3.9213 -1.17161 3.9213 0.119552 4.41146 0.119552C4.66252 0.119552 4.87771 -0.107597 4.87771 -0.310834C4.87771 -0.37061 4.87771 -0.394521 4.79402 -0.573848C4.47123 -1.39875 4.47123 -2.4269 4.47123 -2.51059C4.47123 -2.58232 4.47123 -3.43113 4.72229 -4.5071H6.06127C6.21669 -4.5071 6.61121 -4.5071 6.61121 -4.88966C6.61121 -5.15268 6.38406 -5.15268 6.16887 -5.15268H2.23562C1.96065 -5.15268 1.55417 -5.15268 1.00423 -4.56687C0.6934 -4.22017 0.310834 -3.58655 0.310834 -3.51482S0.37061 -3.41918 0.442341 -3.41918C0.526027 -3.41918 0.537983 -3.45504 0.597758 -3.52677C1.21943 -4.5071 1.8411 -4.5071 2.13998 -4.5071H2.82142C2.55841 -3.61046 2.25953 -2.57036 1.2792 -0.478207C1.18356 -0.286924 1.18356 -0.263014 1.18356 -0.191283C1.18356 0.0597758 1.39875 0.119552 1.50635 0.119552C1.85305 0.119552 1.94869 -0.191283 2.09215 -0.6934C2.28344 -1.30311 2.28344 -1.32702 2.40299 -1.80523L3.09639 -4.5071Z' id='math2-g0-25'/>
            <path d='M5.26027 -2.00847H4.99726C4.96139 -1.80523 4.86575 -1.1477 4.7462 -0.956413C4.66252 -0.848817 3.98107 -0.848817 3.62242 -0.848817H1.41071C1.7335 -1.12379 2.46276 -1.88892 2.7736 -2.17584C4.59078 -3.84956 5.26027 -4.47123 5.26027 -5.65479C5.26027 -7.02964 4.17235 -7.95019 2.78555 -7.95019S0.585803 -6.76663 0.585803 -5.73848C0.585803 -5.12877 1.11183 -5.12877 1.1477 -5.12877C1.39875 -5.12877 1.70959 -5.30809 1.70959 -5.69066C1.70959 -6.0254 1.48244 -6.25255 1.1477 -6.25255C1.0401 -6.25255 1.01619 -6.25255 0.980324 -6.2406C1.20747 -7.05355 1.85305 -7.60349 2.63014 -7.60349C3.64633 -7.60349 4.268 -6.75467 4.268 -5.65479C4.268 -4.63861 3.68219 -3.75392 3.00075 -2.98879L0.585803 -0.286924V0H4.94944L5.26027 -2.00847Z' id='math2-g1-50'/>
          </defs>
          <g id='math2-page1'>
            <use x='0' xlink:href='#math2-g1-50' y='0'/>
            <use x='5.85299' xlink:href='#math2-g0-25' y='0'/>
          </g>
        </svg> with the <svg class="m-math m-warning" style="vertical-align: -0.0pt;" height='6.43422pt' version='1.1' viewBox='0 -5.14737 6.41894 5.14737' width='8.02368pt'>
          <title>LaTeX Math</title>
          <desc>\tau</desc>
          <defs>
            <path d='M3.43113 -4.5071H5.41569C5.57111 -4.5071 5.96563 -4.5071 5.96563 -4.88966C5.96563 -5.15268 5.73848 -5.15268 5.52329 -5.15268H2.23562C1.96065 -5.15268 1.55417 -5.15268 1.00423 -4.56687C0.6934 -4.22017 0.310834 -3.58655 0.310834 -3.51482S0.37061 -3.41918 0.442341 -3.41918C0.526027 -3.41918 0.537983 -3.45504 0.597758 -3.52677C1.21943 -4.5071 1.8411 -4.5071 2.13998 -4.5071H3.13225L1.88892 -0.406476C1.82914 -0.227148 1.82914 -0.203238 1.82914 -0.167372C1.82914 -0.0358655 1.91283 0.131507 2.15193 0.131507C2.52254 0.131507 2.58232 -0.191283 2.61818 -0.37061L3.43113 -4.5071Z' id='math3-g0-28'/>
          </defs>
          <g id='math3-page1'>
            <use x='0' xlink:href='#math3-g0-28' y='0'/>
          </g>
        </svg> character.</p>

.. note-warning::

    Producing SVG manually using command-line tools is no fun, so m.css
    provides a `Pelican plugin <{filename}/plugins/math-and-code.rst#math>`__
    that integrates LaTeX math directly into your markup. Check it out!

`Padding`_
==========

Similarly to `typography elements <{filename}/css/typography.rst#padding>`_;
blocks, notes, frames, tables, images, figures, image grids, code and math
blocks and code figures have :css:`1rem` padding after, except when they are
the last element, to avoid excessive spacing.

`Responsive utilities`_
=======================

If you have some element that will certainly overflow on smaller screen sizes
(such as wide table or image that can't be scaled), wrap it in a
:css:`.m-scroll`. This will put a horizontal scrollbar under in case the
element overflows.

There's also :css:`.m-fullwidth` that will make your element always occupy 100%
of the parent element width. Useful for tables or images.
