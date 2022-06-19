### Widgets Registered

For example, used with registering sidebars:

```markdown

function mytheme_widgets_init() {
    register_sidebar( array(
        'name'          => __( 'Single Post Widgets', 'textdomain' ),
        'id'            => 'mytheme-single-post-widgets',
        'description'   => __( 'Widgets in this area will be shown under your single posts, before comments.', 'textdomain' ),
        'before_widget' => '',
        'after_widget'  => '',
        'before_title'  => '',
        'after_title'   => '',
    ) );
}
add_action( 'widgets_init', 'mytheme_widgets_init' );

```

Display sidebars

```markdown

<?php
  if(is_active_sidebar("mytheme-single-post-widgets")){
    dynamic_sidebar("mytheme-single-post-widgets");
  }
?>

```

