---
layout: discord-redirect
title: Discord Redirect
permalink: /discord/
discord_invite: invite
---

{% assign discord_invite = site.data.discord[page.discord_invite] %}
<script type="text/javascript">
    window.location.href = "{{ discord_invite.domain }}{{ discord_invite.ingredient }}";
</script>
If you are not redirected automatically, follow this <a href="{{ discord_invite.domain }}{{ discord_invite.ingredient }}">link to our discord server</a>.