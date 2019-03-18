# WIRESHARK

Filtro por IP:  
``ip.addr == 192.168.0.200``

Filtro por mais de um IP:  
``ip.addr == 192.168.0.200 && ip.addr == 192.168.0.1``  
``ip.addr == 192.168.0.200 or ip.addr == 192.168.0.201``

Filtro por protocolo:  
``ftp && ip.addr == 192.168.0.200``

Filtro por IP origim:  
``ip.src == 192.168.0.200``

Filtro por IP de destino:  
``ip.dst == 192.168.0.200``

Pesquisa de string em pacotes TCP:  
``tcp contains PASS``  
``tcp contains USER``  
``tcp contains bomba``  

Pesquisa por requisições HTTP:  
``http.request``  

Pesquisa por string na URL de requisições HTTP:  
``http.request.uri.contains default``  
``http.request.uri.contains hacker``  

Filtros do exibição do Wireshark consulte:  
https://wiki.wireshark.org/DisplayFilters

Filtros de captura do Wireshark consulte:  
https://wiki.wireshark.org/CaptureFilters
