---
title: Contact
layout: page
---

<fieldset>
  <p>Envoyez-nous un petit mail, ça fait toujours plaisir :)</p>
  <form action="//formspree.io/contact@sudweb.fr" method="POST">
    <p><label for="_replyto">Votre adresse email :</label><br>
      <input type="email" name="_replyto">
    </p>
    <p><label for="message">Votre message :</label><br>
      <textarea name="message" rows="5" placeholder="Tapez votre texte ici">
      </textarea>
    </p>
    <input type="hidden" name="_subject" value="Message envoyé depuis la page
     contact" />
    <input type="text" name="_gotcha" style="display:none">
    <input type="hidden" name="_next" value="http://sudweb.fr" />
    <p><input class="button" type="submit" value="Envoyer"></p>
  </form>
</fieldset>
