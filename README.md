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

-----------------------another error code   I thihk I fixed this ???-----------------------

function my_styles() {
  wp_enqueue_style('my-style', get_theme_file_uri('/style.css'));
}
add_action( 'wp_enqueue_scripts', 'my_styles' );

function add_google_fonts() {
    wp_enqueue_style( ' add_google_fonts ', 'https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400;600&display=swap', false );
}

add_action( 'wp_enqueue_scripts', 'add_google_fonts' );


function my_scripts() {

// Bootstrap CSS reading First// 
  wp_enqueue_style( 'bootstrap-style', get_template_directory_uri().'/css/bootstrap.css', array(), '1' );

// Bootstrap CSS reading for Customize Second//
  wp_enqueue_style( 'stylesheet-style', get_template_directory_uri().'/css/bootstrap.custom.css', array(), '1' );

// Overwite css file to read// Third
  wp_enqueue_style( 'overwrite-stylesheet-style', get_template_directory_uri().'/css/overwrite.css', array(), '1' );

// Bootstrap JavaScript reading// Fourth
  wp_enqueue_script( 'bootstrap-script', get_template_directory_uri().'/js/bootstrap.min.js', array('jquery'), '4.5.0', true );

}

add_action( 'wp_enqueue_scriots', 'my_bootstrap_scripts');
