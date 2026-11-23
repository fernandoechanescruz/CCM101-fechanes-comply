# Reflection

A host-based firewall protects a server even when the physical network perimeter has been breached, because it enforces security on the server itself instead of only at the network's edge. If an attacker slips past a router or network firewall and reaches the machine directly, UFW still checks every connection attempt against its own rules and drops anything that has not been explicitly allowed. The server never simply trusts the network it sits on.

Managing open network ports is essential for shrinking a server's attack surface, since every open port is a possible way in. A port running a service with a known vulnerability practically invites an attacker. Closing every port except the ones the server truly needs removes whole categories of attack before they can even be tried.

Leaving a database port such as 3306 open to the public internet is dangerous because anyone online can try to connect straight to the database and skip the application layer completely. Databases often store the most sensitive data in a system. One that is directly exposed to brute-force login attempts or known exploits can be compromised without an attacker ever touching the web application in front of it.

Finishing this mission changed how I see the ease of compromising a server. Before setting up UFW myself, I did not fully realize that a freshly deployed server is vulnerable the moment it goes online, and not only after months of neglect. One missed step, such as enabling the firewall before allowing SSH, can lock an administrator out just as easily as a misconfigured rule can leave a server wide open.

My GitHub portfolio now shows eight completed missions, each one building on the one before it, from basic Linux navigation in Mission 1 through infrastructure as code, observability, and now security hardening. Looking at the repository as a whole, it feels less like a collection of unrelated assignments and more like a steady progression toward real cloud engineering practice.
