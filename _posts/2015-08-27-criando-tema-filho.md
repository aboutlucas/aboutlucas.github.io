---
layout: post
title: "Criando Tema Filho do StoreFront"
date: 2015-08-27 20:51:00
image: '/assets/img/'
description: 'Como criar o theme child do StoreFront'
tags:
- Theme
- StoreFront
- WooCommerce
categories:
- Wordpress
twitter_text: 'Put your twitter description here.'
---

Se quiser pular a explicação e ver como ele fica ta ae: [ThemeChild](https://github.com/aboutlucas/Arquivos-do-Blog/tree/master/theme-child/).

## Introdução

O [WooCommerce StoreFront](http://www.woothemes.com/storefront/), é um ótimo plugin para Ecommerce, porém para alterar algumas coisas é preciso criar um tema.

### Nosso Tema Filho vai precisar desses arquivos:

- style.css
- rlt.css
- functions.php
- index.php

**Todos eles devem estar em uma pasta dentro de theme e devem seguir o mesmo nome que os originais**

### style.css

Va a pasta que você criou dentro de theme e crie um arquivos chamado `style.css`, nele você inseri o código abaixo

{% highlight css %}
/*
 Theme Name:  Storefront Child
 Theme URI:    http://www.woothemes.com/storefront-child/
 Description:  WooThemes Child Theme
 Author:         Seu Nome
 Author URI:   http://example.com
 Template:     storefront
 Version:    1.4.6 
 License:      GNU General Public License v2 or later
 License URI:  http://www.gnu.org/licenses/gpl-2.0.html
 Tags:         tags1,tag2, coloque o que achar importante aqui
 Text Domain: storefront-child
*/
{% endhighlight css %}

Nessas linhas de comentários é necessário atualizar o Version, caso seu storefront use uma versão mais recente,
qualquer coisa só verificar na pasta dele e ver como está.

**Se você quiser criar um tema filho, qualquer seja o tema pai é só seguir esse processo que estou fazendo**
**Porém nos Coméntarios devem ser alterados Template, Version, Theme URI**

### rlt.css

Esse arquivo é um suporte de idiomas

{% highlight css %}
/*
Theme Name: StoreFront Child
Template: storefront
*/
{% endhighlight css %}

### functions.php

A função inicial dele vai ser fazer com que as alterações efetuadas no `style.css` do tema filho sejam carregadas no tema pai

{% highlight php %}
<?php
add_action( 'wp_enqueue_scripts', 'theme_enqueue_styles' );
function theme_enqueue_styles() {
    wp_enqueue_style( 'parent-style', get_template_directory_uri() . '/style.css' );
}
?>
{% endhighlight php %}

### index.php

Esse é o arquivo modelo

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

## Conclusão

Um tema filho nada menos é que o `style.css` +  `functions.php` + `index.php` dentro de uma pasta na pasta theme.

### Observação:
Se você atualizar o tema é preciso ir até a pasta do tema filho e editar a Version do style.css 
para a Version que o seu tema está.

Logo eu faço uma série de como instalar WooCommerce.

Até logo.
