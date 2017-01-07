---
title: Contact
permalink: "/contact/"
layout: page
draft: false
---

<fieldset>
  <p>Une question, une proposition, des calins, recevoir un petit mail ça nous fait toujours plaisir.</p>
  <form action="//formspree.io/contact@sudweb.fr" method="POST">
    <p><label class="desc" for="_replyto">Votre adresse email :</label><br>
      <input type="email" name="_replyto" placeholder="contact@sudweb.fr">
    </p>
    <p><label class="desc" for="message">Votre message :</label><br>
      <textarea name="message" rows="" placeholder="Tapez votre texte ici"></textarea>
    </p>
    <input type="hidden" name="_subject" value="Message envoyé depuis la page
     contact" />
    <input type="text" name="_gotcha" style="display:none">
    <input type="hidden" name="_next" value="http://sudweb.fr" />
    <p><input class="button-type1" type="submit" value="Envoyer"></p>
  </form>
</fieldset>
