**How do I display featured image in inline style markup?**

```markdown

<?php $image = wp_get_attachment_image_src( get_post_thumbnail_id(get_the_ID())); echo $image[0];?>

```
