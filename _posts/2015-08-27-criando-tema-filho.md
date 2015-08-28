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

Se quiser pular a explicação e ver como ele fica ta ae : [Theme Child](https://github.com/aboutlucas/loja/tree/master/).
Senão é uma coisa bem rápida de se fazer, tem algumas observações que você precisa está ciente, vamos começar.

Vá até a pasta theme, nela crie uma nomeie como quiser, nesta pasta você deve passar copiar e colar os arquivos do tema que está usando,
Os arquivos principais que devem ser passados para não gerar nenhum problema são:

- Style.css
- Rtl.css
- Index.php
- Functions.php

O [wordpress](https://codex.wordpress.org/Child_Themes/) tem um exemplo de como criar, só estou repassando com algumas coisas importantes.
O style.css que você passou para a sua pasta apague tudo e deixe só o cabeçalho, se tirar o cabeçalho o wordpress não vai reconhecer que é um
tema filho pois não tem a descrição do tema.
Um exemplo de como fica o style.css:

{% highlight css %}
/*
 Theme Name:   Twenty Fifteen Child
 Theme URI:    http://example.com/twenty-fifteen-child/
 Description:  Twenty Fifteen Child Theme
 Author:       John Doe
 Author URI:   http://example.com
 Template:     twentyfifteen
 Version:      1.0.0
 License:      GNU General Public License v2 or later
 License URI:  http://www.gnu.org/licenses/gpl-2.0.html
 Tags:         light, dark, two-columns, right-sidebar, responsive-layout, accessibility-ready
 Text Domain:  twenty-fifteen-child
*/
{% endhighlight %}

Um exemplo do rtl.css:

{% highlight css%}
/*
Theme Name: Twenty Fourteen Child
Template: twentyfourteen
*/
{% endhighlight %}

Algo bem simples de se fazer, agora embaixo você adiciona as alterações que deseja fazer.
Para que elas sejam aplicadas necessita de uma função, então vamos criar o functions.php.

{% highlight css %}
add_action( 'wp_enqueue_scripts', 'theme_enqueue_styles' );
function theme_enqueue_styles() {
    wp_enqueue_style( 'parent-style', get_template_directory_uri() . '/style.css' );

}
{% endhighlight %}

Agora todas as alterações que você fizer no seu style.css. Porém vai dar um erro de que não há arquivo modelo,
você precisa copiar a index.php do seu tema e por em sua pasta.

Acabou, está feito o tema filho, mas se deseja fazer alguma outra alteração como por exemplo o rodapé, é só copiar o footer.php e 
alterar a linha 15, (depedendo do tema a linha de alteração pode mudar mas, é por esse mesmo caminho) no meu caso estou usando 
o footer.php do store front.

