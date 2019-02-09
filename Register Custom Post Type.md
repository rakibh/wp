## Custom Post Type Register


### Sort
```PHP
function neuron_custom_post()
{
    register_post_type('wporg_product',
        array(
            'labels' => array(
                'name' => __('Products'),
                'singular_name' => __('Product'),
            ),
            'public' => true,
            'has_archive' => true,
        )
    );
}
add_action('init', 'neuron_custom_post');
```

<br>


### A Custom Slug for a Custom Post Type
```PHP
function neuron_custom_post()
{
    register_post_type('wporg_product',
        array(
            'labels' => array(
                'name' => __('Products'),
                'singular_name' => __('Product'),
            ),
            'public' => true,
            'has_archive' => true,
            'rewrite'     => array( 'slug' => 'products' ), // my custom slug
        )
    );
}
add_action('init', 'neuron_custom_post');
```

<br>


### Custom Post Type with all 
```PHP
function neuron_custom_post() {

    $labels = array(
        'name'               => __( 'Plural Name', 'text-domain' ),
        'singular_name'      => __( 'Singular Name', 'text-domain' ),
        'add_new'            => _x( 'Add New Singular Name', 'text-domain', 'text-domain' ),
        'add_new_item'       => __( 'Add New Singular Name', 'text-domain' ),
        'edit_item'          => __( 'Edit Singular Name', 'text-domain' ),
        'new_item'           => __( 'New Singular Name', 'text-domain' ),
        'view_item'          => __( 'View Singular Name', 'text-domain' ),
        'search_items'       => __( 'Search Plural Name', 'text-domain' ),
        'not_found'          => __( 'No Plural Name found', 'text-domain' ),
        'not_found_in_trash' => __( 'No Plural Name found in Trash', 'text-domain' ),
        'parent_item_colon'  => __( 'Parent Singular Name:', 'text-domain' ),
        'menu_name'          => __( 'Plural Name', 'text-domain' ),
    );

    $args = array(
        'labels'              => $labels,
        'hierarchical'        => false,
        'description'         => 'description',
        'taxonomies'          => array(),
        'public'              => true,
        'show_ui'             => true,
        'show_in_menu'        => true,
        'show_in_admin_bar'   => true,
        'menu_position'       => null,
        'menu_icon'           => null,
        'show_in_nav_menus'   => true,
        'publicly_queryable'  => true,
        'exclude_from_search' => false,
        'has_archive'         => true,
        'query_var'           => true,
        'can_export'          => true,
        'rewrite'             => true,
        'capability_type'     => 'post',
        'supports'            => array(
            'title',
            'editor',
            'author',
            'thumbnail',
            'excerpt',
            'custom-fields',
            'trackbacks',
            'comments',
            'revisions',
            'page-attributes',
            'post-formats',
        ),
    );

    register_post_type( 'slug', $args );
}

add_action( 'init', 'neuron_custom_post' );
```

<br>
WP Ref:
https://developer.wordpress.org/reference/functions/register_post_type/
https://developer.wordpress.org/plugins/post-types/registering-custom-post-types/
https://codex.wordpress.org/Function_Reference/register_post_type