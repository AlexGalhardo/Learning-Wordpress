## References

 - Recommended Courses
    - [Origamid - Wordpress como CMS](https://www.origamid.com/curso/wordpress-como-cms)
 - Configuration Tutorials
    - Configure FTP Localhost
       - [LocalHost Docs Transfer Files FTP](http://localhost/dashboard/docs/transfer-files-ftp.html)
 - Migration
    - https://goodbye.host/file
 - URLs
    - http://localhost/wordpress/wp-admin
    - http://localhost/wordpress/wp-login
    - http://localhost/wordpress/wp-json
 - Usefull Tools
    - https://cyberduck.io/
    - https://filezilla-project.org/
 - Usefull Oficial Tutoriais
    - https://codex.wordpress.org/Theme_Development
    - https://codex.wordpress.org/pt-br:O_Loop
    - https://wordpress.org/about/requirements/
    - https://wphierarchy.com/
 - Others Tutorials
    - http://www.wp24horas.com.br/tutoriais/como-habilitar-emails-wordpress-localhost-usando-xampp
    - https://www.hostinger.com.br/tutoriais/aprenda-a-utilizar-o-smtp-google/
 - Recommended Hosts
    - https://br.bluehost.com/
    - https://king.host/hospedagem-de-sites
    - https://mediatemple.net/webhosting/managed-wordpress
    - https://www.dreamhost.com/wordpress/
    - https://www.hostgator.com.br/
    - https://www.digitalocean.com/
    - https://www.umbler.com/br
 - Sites
    - [WP Beginner](https://www.wpbeginner.com/)
    - [WP Cli](http://wp-cli.org/)
    - [ManageWP](https://managewp.com/)
    - [WPEngine](https://wpengine.com/)
 - Blogs
    - https://claudiosanches.com/
 - Recommended Plugins
    - [JetPack](https://jetpack.com/)
    - [WP-Mail-SMTP](https://wordpress.org/plugins/wp-mail-smtp/)
    - [W3 Total Cache](https://wordpress.org/plugins/w3-total-cache/)
    - [Duplicator](https://wordpress.org/plugins/duplicator/)
    - [Contact Form 7](https://wordpress.org/plugins/contact-form-7/)
    - [Loco Translate](https://br.wordpress.org/plugins/loco-translate/)
    - [Weglot Translate](https://pt.wordpress.org/plugins/weglot/)
    - [WP Super Cache](https://wordpress.org/plugins/wp-super-cache/)
    - [StarRating](https://wordpress.org/plugins/yet-another-stars-rating/)
    - [All in One Schema rich snipptets](https://wordpress.org/plugins/all-in-one-schemaorg-rich-snippets/?utm_source=blog&utm_campaign=rc_blogpost)
    - [Advanced Custom Fields](https://www.advancedcustomfields.com/)
    - [AMP for WP – Accelerated Mobile Pages](https://br.wordpress.org/plugins/accelerated-mobile-pages/)
    - [Woocomerce](https://woocommerce.com)
    - [WPTouch](https://br.wordpress.org/plugins/wptouch)
    - [Yoast SEO Plugin](https://yoast.com/wordpress/plugins/seo/)
    - [Autoptimize](https://wordpress.org/plugins/autoptimize/)
    - [EWWW Image Optimizer](https://br.wordpress.org/plugins/ewww-image-optimizer/)
    - [Duplicator](https://br.wordpress.org/plugins/duplicator/)
 - WooCommerce
    - https://woocommerce.com/products/sensei/
 - Themes
    - [ThemeForest](http://themeforest.net/category/wordpress)
    - [ThemeFuse](http://themefuse.com/)
 - Security & Backups
    - [Sucuri](https://sucuri.net/)
    - https://vaultpress.com/
 - CDN
    - [CloudFlare](https://www.cloudflare.com/pt-br/)
    - [StackPath](https://www.stackpath.com/)
 - Forum
    - [BBPress](https://bbpress.org/)
  - Checklist
    - [WP Security Checklist](https://wpsecuritychecklist.org/br/items/)

## Criando Temas Wordpress - Curso Origamid
```
// Instalar o Wordpress

1 - Download do Wordpress (wordpress.org)

2 - Criar uma pasta do repositório de sites do MAMP

3 - Extrair os arquivos do Wordpress nela

4 - Criar um Banco de Dados no phpMyAdmin
Abra o phpMyAdmin > Databates > Escolha o nome > Clique em Create

5 - Criar o usuário do Banco de Dados
phpMyAdmin > Users > Add User > Nome, host(localhost), password.
Maque Check All em Global Privileges

6 - Acessar o site e instalar o Wordpress

7 - Criar o usuário do wordpress

// Após Instalar o Wordpress

1 - Copiar a pasta do site para wp-content/themes/

2 - Mudar o index.html para index.php

3 - Colocar/criar o arquivo style.css na raiz do tema
@import 'css/reset.css';

4 - Adicionar a descrição do tema no topo do style.css
/*
Theme Name: Rest
Theme URI: http://rest.com
Author: André Rafael
Author URI: http://origamid.com/
Description: Tema criado para o restaurante Rest
Version: 1.0
*/

5 - Ativar o tema no Wordpress

6 - Corrigir o caminho do style.css e outros caminhos se necessário
<?php echo get_stylesheet_directory_uri(); ?>
Essa função adiciona o caminho até a raiz do tema

7 - Separar o header e footer em arquivos header.php e footer.php
Adicionar antes de fechar o head: <?php wp_head(); ?>
Adicionar antes de fechar o body: <?php wp_footer(); ?>
Adicionar o header e footer nas páginas do site e mudá-las para .php
Com <?php get_header(); ?> e <?php get_footer(); ?>

8 - Começar a substituir o conteúdo por funções de Wordpress

<?php bloginfo('name'); ?>
Mostra o nome do blog

9 - Transformar as páginas em HTML, em templates de Páginas
A página index.php deve estar reservada para conteúdo genérico.
Adicionar o nome page- na frente de cada template de página para facilitar a organização.
<?php
// Template Name: Sobre
?>

10 - Adicionar as páginas na interface do Wordpress

11 - Adicionar o Loop
O Loop é utilizado para mostrar o conteúdo dos posts,
ele é inteligente o suficiente para saber se precisa mostrar apenas um ou uma sequência.

Adicionar o Loop as páginas e ao index.php

<?php if ( have_posts() ) : while ( have_posts() ) : the_post(); ?>
	
	<?php the_title(); ?>
	<?php the_content(); ?>

<?php endwhile; else: ?>
<p><?php _e('Sorry, no posts matched your criteria.'); ?></p>
<?php endif; ?>


*Pega o diretório do template
<?php echo get_template_directory_uri(); ?>

12 - Advanced Custom Fields

Adicionar o Plugin Advanced Custom Fields Pro
(Nota: O Pro é pago e só pode ser utilizado nos arquivos do curso).
(Existem alternativas, mas a lógica é a mesma)

Iniciar a troca do conteúdo por fields, <?php the_field('nome_conteudo'); ?>
Adicionar o conteúdo a interface do Custom Fields.

Podemos criar partes do site que podem ser adicionadas via função PHP include.

include(TEMPLATEPATH . '/inc/introducao.php');


13 - Repeater Field

<?php if(have_rows('nomedorepeater')): while(have_rows('nomedorepeater')) : the_row(); ?>
	
	the_sub_field('nomedocampo');

<?php endwhile; else : endif; ?>

14 - Pegar valores de outras páginas

<?php
	$contato = get_page_by_title('contato');
	the_field('telefone', $contato)
?>

Verificar se é a página

if(is_page('sobre')) {

}

Não é a página
if(!is_page('sobre')) {

}


15 - Terminar de adicionar os outros campos
<?php echo date("Y"); ?> (Mostrar a data)


// Altera css com um custom field
<style type="text/css">
  .titulo {
    background-image: url(“<?php the_field(‘background’); ?>”);
  }
</style>

// Mostrar imagens de tamanhos diferentes
<?php
$imagem_id = get_field(‘imagem’);
$imagem_grande = wp_get_attachment_image_src( $imagem_id, ‘grande’ );
$imagem_pequena = wp_get_attachment_image_src( $imagem_id, ‘pequena’ );
?>

<?php echo $imagem_grande[0]; ?>


// Adicionar tamanhos de imagens
function my_custom_sizes() {
  add_image_size( ‘grande’, 1400, 460, true );
  add_image_size( ‘pequena’, 360, 260, true );
}
add_action( 'after_setup_theme', 'my_custom_sizes' );

large
medium
thumb



16 - Adicionar campos para SEO
<title><?php bloginfo('name'); ?> - <?php wp_title(''); ?> <?php the_field('title_seo'); ?></title>
<meta name="description" content="<?php bloginfo('name'); ?> - <?php wp_title(''); ?> <?php the_field('description_seo'); ?>">

17 - Adicionar o Functions.php

// Funções para Limpar o Header
remove_action('wp_head', 'rsd_link');
remove_action('wp_head', 'wlwmanifest_link');
remove_action('wp_head', 'start_post_rel_link', 10, 0 );
remove_action('wp_head', 'adjacent_posts_rel_link_wp_head', 10, 0);
remove_action('wp_head', 'feed_links_extra', 3);
remove_action('wp_head', 'wp_generator');
remove_action('wp_head', 'print_emoji_detection_script', 7);
remove_action('admin_print_scripts', 'print_emoji_detection_script');
remove_action('wp_print_styles', 'print_emoji_styles');
remove_action('admin_print_styles', 'print_emoji_styles');

18 - Adicionar Custom Post Types

function custom_post_type_produtos() {
	register_post_type('produtos', array(
		'label' => 'Produtos',
		'description' => 'Produtos',
		'public' => true,
		'show_ui' => true,
		'show_in_menu' => true,
		'capability_type' => 'post',
		'map_meta_cap' => true,
		'hierarchical' => false,
		'rewrite' => array('slug' => 'produtos', 'with_front' => true),
		'query_var' => true,
		'supports' => array('title', 'editor', 'page-attributes','post-formats'),

		'labels' => array (
			'name' => 'Produtos',
			'singular_name' => 'Produto',
			'menu_name' => 'Produtos',
			'add_new' => 'Adicionar Novo',
			'add_new_item' => 'Adicionar Novo Produto',
			'edit' => 'Editar',
			'edit_item' => 'Editar Produto',
			'new_item' => 'Novo Produto',
			'view' => 'Ver Produto',
			'view_item' => 'Ver Produto',
			'search_items' => 'Procurar Produtos',
			'not_found' => 'Nenhum Produto Encontrado',
			'not_found_in_trash' => 'Nenhum Produto Encontrado no Lixo',
		)
	));
}
add_action('init', 'custom_post_type_produtos');

O template utilizado é single-slug.php (ou index.php caso não exista)

<?php
	$args = array (
		'post_type' => 'produtos',
		'order'   => 'ASC'
	);
	$the_query = new WP_Query ( $args );
?>

<?php if ( $the_query->have_posts() ) : while ( $the_query->have_posts() ) : $the_query->the_post(); ?>
	<h1><?php the_title(); ?></h1>
<?php endwhile; else: endif; ?>

// Reset o Loop
<?php wp_reset_query(); wp_reset_postdata(); ?>

19 - Adicionar o Menu

// Habilitar Menus
add_theme_support('menus');

// Registrar o Menu
function register_my_menu() {
  register_nav_menu('header-menu',__( 'Header Menu' ));
}
add_action( 'init', 'register_my_menu' );

<?php
	$args = array(
		'menu' => 'principal',
		'theme_location' => 'menu-principal',
		'container' => false
	);
	wp_nav_menu( $args );
?>

Adicionar o css
.current_page_item a

20 - Adicionar o JS e o CSS da forma correta

// Registrar o CSS e o JS
function bikcraft_scripts() {
	// Desregistra o jQuery do Wordpress
	wp_deregister_script('jquery');

	// Registra o jQuery Novo
	wp_register_script( 'jquery', get_template_directory_uri() . '/js/libs/jquery-1.11.2.min.js', array(), "1.11.2", true );

	// Registra o Script de Plugins, com dependência do jquery, sem especificar versão e no footer do site
	wp_register_script( 'plugins-script', get_template_directory_uri() . '/js/plugins.js', array( 'jquery' ), false, true );

	// Registra o Script Principal, com dependência do jquery e plugins, sem especificar versão e no footer do site
	wp_register_script( 'main-script', get_template_directory_uri() . '/js/main.js', array( 'jquery', 'plugins-script' ), false, true );

	// Coloca script no site
	wp_enqueue_script( 'main-script' );
}
add_action( 'wp_enqueue_scripts', 'bikcraft_scripts' );


21 - Adicionar o SEO

<?php wp_title(''); ?>

<link rel="shortcut icon" href="<?php echo get_stylesheet_directory_uri(); ?>/favicon.ico" />

Adicionar a imagem ao tema

22 - Adicionar o blog

Criar uma página especifica para o blog e adicionar ela nas Configurações > Leitura

```

