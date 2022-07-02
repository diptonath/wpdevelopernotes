#### Custom Post URL rewrite filter hook(LWHH-21.10)

```markdown

function clarencetaylor_link_fix($post_link, $id){
  $p = get_post($id);
  if(is_object($p) && 'chapter' == get_post_type($id)){
    $parent_post_id = get_field('parent_book');
    $parent_post = get_post($parent_post_id);
    if($parent_post){
      $post_link = str_replace("%book%", $parent_post->post_name,$post_link);
    }
    return $post_link;
  }
}
add_filter('post_type_link', 'clarencetaylor_link_fix',1,2 );

```


