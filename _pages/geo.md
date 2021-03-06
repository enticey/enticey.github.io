---
layout: page
title: IP Geolocation
permalink: /geo/
---

<script src="https://cdn.jsdelivr.net/npm/jquery@3.5.1/dist/jquery.min.js" integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous"></script>
<script>
    $.getJSON("https://ipgeolocation.abstractapi.com/v1/?api_key=a11bf66a7e494010a785f9eea3a8dd78", function(data) {
        // Much better ways to do this but it'll work for now.
        data.ip_address = "<strong>IP Address:</strong><span style='color: #86DE74;'> " + data.ip_address + "</span>";
        data.security.is_vpn = "<br/><strong>Using VPN:</strong><span style='color: #FF7DE9;'> " + data.security.is_vpn + "</span>";
        data.region = "<br/><strong>Region:</strong><span style='color: #FF7DE9;'> " + data.region + ", " + data.region_iso_code + "</span>";
        data.timezone.name = "<br/><strong>Timezone:</strong><span style='color: #FF7DE9;'> " + data.timezone.name + "</span>";
        data.connection.autonomous_system_number = "<br/><strong>ASN:</strong><span style='color: #86DE74;'> " + data.connection.autonomous_system_number + "</span>";
        data.connection.organization_name = "<br/><strong>Organization/ISP:</strong><span style='color: #FF7DE9;'> " + data.connection.organization_name + "</span>";
        // Nothing to really do with geo but I can see it being useful for something.
        var user_agent = "<br/><strong>User-Agent:</strong><span style='color: #FF7DE9;'> " + navigator.userAgent + "</span>";

        document.getElementById("ipgeo").innerHTML = 
                                                    data.ip_address +
                                                    data.security.is_vpn +
                                                    data.region +
                                                    data.timezone.name +
                                                    data.connection.autonomous_system_number +
                                                    data.connection.organization_name +
                                                    user_agent;
    })
</script>

<div class="language-plaintext highlighter-rouge">
    <div class="highlight">
        <pre class="highlight"><code><p id="ipgeo"></p><br/><i>Big thanks to AbstractAPI for fetching this data for us, we store none of it.</i></code></pre>
    </div>
</div>