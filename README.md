<h2>Criteo Dynamic Loader OneTag Implementasyonu</h2>

Criteo OneTag'in doğru şekilde çalışabilmesi için iki farklı kodun web sitesine eklenmesi gerekmektedir. Bunlardan birisi yükleyici komut dosyasıdır, diğeri ise veri toplamak için gereklidir.

   

     <script type="text/javascript" src="//static.criteo.net/js/ld/ld.js"async="true"></script>

  
1.  Markalarımızda bulunan mevcut yükleyici statik kod <body> bölümünde olup, yukarıda belirtilen şekilde bulunmaktadır. Bu kodun kaldırılması gerekmektedir.
   

    <script type="text/javascript" src="//dynamic.criteo.com/js/ld/ld.js?a=YOUR_PARTNER_ID" async="true"></script>
  
2.  Yukarıda belirtilen kod, web sitesinin <head> bölümüne dahil edilmeli ve tüm sayfalarda çalıştırılmalıdır.
    
         <script type="text/javascript"> window.criteo_q = window.criteo_q || []; var deviceType = /iPad/.test(navigator.userAgent) ? "t" : /Mobile|iP(hone|od)|Android|BlackBerry|IEMobile|Silk/.test(navigator.userAgent) ? "m" : "d"; window.criteo_q.push( { event: "setAccount", account: YOUR_PARTNER_ID}, { event: "setEmail", email: "##Email Address##" }, { event: "setSiteType", type: deviceType}, { event: "viewPage" } ); </script>

3.  Yukarıdaki ziyaret etiketi (visit tag), başka bir Criteo etiketi içermeyen tüm sayfalarda tetiklenmesi gerekmektedir.`
