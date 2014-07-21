Process404Search
================

Processwire module for loading search results into 404 page using terms from the failed URL

After installing you must choose your search page from the module config settings.

Next, you must edit your search template (most likely search.php) and add this as the first line:
```
if(isset($options['q'])) $input->get->q = $options['q'];
```

Alternatively, you could use the following, to also include your "404 Page Not Found" page's body field. This needs to be after $out is initially defined in the search.php file:
```
if(isset($options['q'])){
    $input->get->q = $options['q'];
    $out .= $pages->get(27)->body;
}
```

You may want to enter something like the following into your 404 Page Not Found page field:

"The page you were looking for is not found.
We have tried to find the content you were looking for, but if we didn't get it right, please use our search engine or navigation above to find the page."


## License

This program is free software; you can redistribute it and/or
modify it under the terms of the GNU General Public License
as published by the Free Software Foundation; either version 2
of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program; if not, write to the Free Software
Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301, USA.

(See included LICENSE file for full license text.)