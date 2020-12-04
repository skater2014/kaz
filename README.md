# kaz
-----------------------error code-----------------------

errpr code Fatal error: Uncaught Error: 


//change category color for diffeently
function categories_label() {
  $cats = get_the_category();
  if(!empty($cats)){
    if(!is_wp_error($cats)){
      foreach($cats as $cat){
        $cat_link = get_category_link($cat->term_id);
        $cat_name = $cat->name;
        $cat_id = $cat->cat_ID;
        $cat_color = 'category_'.$cat_id;
        $back_color = get_field('ca_color_band',$cat_color);
        $txt_color = get_field('ca_color_txt',$cat_color);
        echo '<span class="category"><a href="'.$cat_link.'" class="rounded_btn" style="background-color:'.$back_color.';color:'.$txt_color.';">'.$cat_name.'</a></span>';

        //inline-block; border-radius: 6px; background-color:'.$back_color.';color:'.$txt_color.';">'.$cat_name.'</a></span>';//
      }
    }
  }
}

$back_color = get_field('ca_color_band',$cat_color);
$txt_color = get_field('ca_color_txt',$cat_color);

