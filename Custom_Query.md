#### WP_Query [Reference](https://developer.wordpress.org/reference/classes/wp_query/)

```markdown

<?php 
    $query = new WP_Query(array(
        'post__in'        => array(59,57,53,27),
        'posts_per_page'  => '3',
        'order'           => 'ASE',
    ));

    while($query->have_posts()){
        $query->the_post();
        ?>
            <h4 class="text-center"><?php the_title(); ?></h4>
        <?php
    }
    wp_reset_query();
?>

```

With WP_Query arguments

```markdown

<?php
    $args = array(
        'post__in'        => array(59,57,53,27),
        'posts_per_page'  => '5',
        'order'           => 'ASE',
    );

    $query = new WP_Query($args);

    while($query->have_posts()){
        $query->the_post();
        ?>
            <h4 class="text-center"><?php the_title(); ?></h4>
        <?php
    }
    wp_reset_query();
?>

```

Display posts that are in the **quotes category** OR have the **quote post tag**:

```markdown

<?php
    $args = array(
        'post_type' => 'post',
        'tax_query' => array(
            'relation' => 'OR',
            array(
                'taxonomy' => 'category',
                'field'    => 'slug',
                'terms'    => array( 'quote' ),
            ),
            array(
                'taxonomy' => 'post_tag',
                'field'    => 'slug',
                'terms'    => array( 'quote' ),
            ),
        ),
    );

    $query = new WP_Query($args);

    while($query->have_posts()){
        $query->the_post();
        ?>
            <h4 class="text-center"><?php the_title(); ?></h4>
        <?php
    }
    wp_reset_query();
?>

```




