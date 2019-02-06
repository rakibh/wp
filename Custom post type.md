### Custom Post Type Register

```
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