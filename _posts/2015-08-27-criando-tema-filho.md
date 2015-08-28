---
layout: post
title: "Criando Tema Filho do Wordpress"
date: 2015-08-27 20:51:00
image: '/assets/img/'
description: 'Como criar o theme child no wordpress'
tags:
- wordpress
- theme
categories:
- Wordpress
twitter_text: 'Put your twitter description here.'
---

Se quiser pular a explicação e ver como ele fica ta ae: [ThemeChild](https://github.com/aboutlucas/Arquivos-do-Blog/tree/master/theme-child/).

# Introdução

Vou usar como exemplo o [WooCommerce StoreFront](http://www.woothemes.com/storefront/), um ótimo plugin para Ecommerce, 
chega de marketing. Tive um problema esses dias, eu tinha que alterar o rodapé storefront, aplicar alguns filtros, porém 
não tinha como eu fazer tudo isso, tive que criar algo para que nesse algo eu pudesse fazer as alterações, o tema filho.

Para criar um tema filho, é necessário ir a pasta theme, depois criar uma outra pasta, nesse exemplo criar uma pasta chamada storefront-child para associar. Depois de cria-la é preciso copiar o cabeçalho do <strong>style.css</strong> do storefront, depois fazer algumas alterações, ficando assim:

{% highlight css %}
/*
 Theme Name:  Storefront Child
 Theme URI:    http://www.woothemes.com/storefront-child/
 Description:  WooThemes Child Theme
 Author:         Lucas Dias
 Author URI:   http://example.com
 Template:     storefront
 Version:    1.4.6 /* É importante modificar o Version se você atualizar o tema. */
 License:      GNU General Public License v2 or later
 License URI:  http://www.gnu.org/licenses/gpl-2.0.html
 Tags:         tags1,tag2, coloque o que achar importante aqui
 Text Domain: storefront-child
*/
{% endhighlight css %}

Depois disso crie um arquivo chamado functions.php e nele uma função para fazer com que as alterações do style.css que você copiou e modificou sejam realizadas.

O <strong>functions.php</strong> fica assim:

{% highlight php %}
<?php
add_action( 'wp_enqueue_scripts', 'theme_enqueue_styles' );
function theme_enqueue_styles() {
    wp_enqueue_style( 'parent-style', get_template_directory_uri() . '/style.css' );
}
?>
{% endhighlight php %}

O functions.php é usado também para fazer algumas alterações no woocommerce, como por exemplo tirar campos, deixar como não obrigatórios, é o functions.php, ele pode customizar o seu woocommerce de acordo com você.

O arquivo modelo <strong>index.php</strong> fica assim:

{% highlight php %}
<?php
/**
 * The main template file.
 *
 * This is the most generic template file in a WordPress theme
 * and one of the two required files for a theme (the other being style.css).
 * It is used to display a page when nothing more specific matches a query.
 * E.g., it puts together the home page when no home.php file exists.
 * Learn more: http://codex.wordpress.org/Template_Hierarchy
 *
 * @package storefront
 */
get_header(); ?>

	<div id="primary" class="content-area">
		<main id="main" class="site-main" role="main">

		<?php if ( have_posts() ) : ?>

			<?php get_template_part( 'loop' ); ?>

		<?php else : ?>

			<?php get_template_part( 'content', 'none' ); ?>

		<?php endif; ?>

		</main><!-- #main -->
	</div><!-- #primary -->

<?php do_action( 'storefront_sidebar' ); ?>
<?php get_footer(); ?>
{% endhighlight php %}

Agora para modificar quais quer arquivos originais do tema é só cria-los lá no filho e inserir o código, 
eu como quero modificar o rodapé eu crio o footer.php copio o original e troco a parte que quero, no caso
eu quero alterar a frase do rodapé para outra coisa, o resultado é esse:

{% highlight php %}
<?php
/**
 * The template for displaying the footer.
 *
 * Contains the closing of the #content div and all content after
 *
 * @package storefront
 */
?>

		</div><!-- .col-full -->
	</div><!-- #content -->

	<?php do_action( 'storefront_before_footer' ); ?>

	<footer id="colophon" class="site-footer" role="contentinfo">
		<div class="col-full">

			<?php
			/**
			 * @hooked storefront_footer_widgets - 10
			 * @hooked storefront_credit - 20
			 */
			echo "&copy; 2015 <a href=#>Ecommerce</a>. Todos os direitos reservados."; ?>

		</div><!-- .col-full -->
	</footer><!-- #colophon -->

	<?php 
		do_action( 'storefront_after_footer' );
 	?>

</div><!-- #page -->

<?php wp_footer(); ?>

</body>
</html>
{% endhighlight php %}


# Conclusão

Um tema filho nada menos é que o style.css + functions.php + index.php dentro de uma pasta na pasta theme.
Logo eu faço uma série de como instalar Woocomerce.

Até logo.
