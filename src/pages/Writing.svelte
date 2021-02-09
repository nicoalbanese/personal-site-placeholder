<script>
    // import fs from "fs";
    // import path from "path";

    import { Posts } from "../../content/_posts.js";
    console.log(Posts);

</script>

<div class="mb-4 text-center">
    <h2 class="text-2xl font-bold mb-2">Writing</h2>
    <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Deserunt porro
        aut ullam explicabo quisquam ea similique rerum excepturi illo vero
        provident, accusamus error blanditiis tempore? Vel iste vero ratione
        voluptas?
    </p>
</div>
<ul><li><a href="/writing/1">Go to post 1</a></li></ul>

<!-- // src/routes/blog/[slug].json.js

import path from "path";
import fs from "fs";
import grayMatter from "gray-matter";
import marked from "marked";
import hljs from "highlight.js";

const getPost = fileName =>
  fs.readFileSync(path.resolve("content", `${fileName}.md`), "utf-8");

export function get(req, res, next) {
  const { slug } = req.params;

  // get the markdown text
  const post = getPost(slug);

  // function that expose helpful callbacks
  // to manipulate the data before convert it into html
  const renderer = new marked.Renderer();
./
  // use hljs to highlight our blocks codes
  renderer.code = (source, lang) => {
    const { value: highlighted } = hljs.highlight(lang, source);
    return `<pre class='language-javascriptreact'><code>${highlighted}</code></pre>`;
  };

  // parse the md to get front matter
  // and the content without escaping characters
  const { data, content } = grayMatter(post);

  const html = marked(content, { renderer });

  if (html) {
    res.writeHead(200, {
      "Content-Type": "application/json"
    });

    res.end(JSON.stringify({ html, ...data }));
  } else {
    res.writeHead(404, {
      "Content-Type": "application/json"
    });

    res.end(
      JSON.stringify({
        message: `Not found`
      })
    );
  }
} -->
