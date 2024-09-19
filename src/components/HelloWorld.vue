<template>
    <div>
      <!-- <p>{{ emailMontado }}</p> -->
        <h1>Monta Email Mkt</h1>
        <ul style="list-style-type: none; border:1px solid grey; background-color:lightgrey; border-radius:25px; padding: 32px 0px; max-width:650px; margin: 0 auto;">
            <li><label for="nome">NOME</label><br><input type="text" v-model="razaoSocial"></li>
            <li><label for="cnpj">CNPJ</label><br><input type="text" v-model="cnpj"></li>
            <li><label for="senha">SENHA</label><br><input type="text" v-model="senha"></li>  
            <li><button style="background-color:darkorange; color:black; margin: 8px 0px" @click="emailMontado = !emailMontado">Gerar</button></li>
          </ul>

          <hr v-show="emailMontado === true" style="margin:8px;">

          <div  v-show="emailMontado === true" style="width:100%; justify-content: center;"><button style="background-color:darkorange;" @click="copiar">Copiar</button></div>

          <hr v-show="emailMontado === true" style="margin:8px;">

        <div v-show="emailMontado === true" style="display:flex; flex-direction: row; justify-content: space-evenly; width:100%;">
         
       

        
        <!-- Área para colar o conteúdo textual do e-mail -->

        <span  v-html="generateHtml"></span>

        <pre style="white-space: pre-wrap; word-wrap: break-word; max-width: 50%; overflow-wrap: break-word; border:1px solid lightgray; background-color: lightgray; border-radius:25px;">

        
        <code id="codeText" >

          {{ escapedHtml }}
        </code>

      </pre>
          
      </div>  


    </div>  
</template>

<script>
name: "montaEmail"
export default {
  data(){
    return{
      razaoSocial : "",
      cnpj: "",
      emailMontado: false,
        senha: "",
    }
  },
  methods:{
    copiar(){
      const textToCopy = this.escapedHtml;
      if (navigator.clipboard && navigator.clipboard.writeText) {
        navigator.clipboard.writeText(textToCopy).then(() => {
          alert('HTML copied to clipboard!');
        }).catch(err => {
          console.error('Failed to copy text: ', err);
        });
      } else {
        // Fallback method for older browsers
        const textarea = document.createElement('textarea');
        textarea.value = textToCopy;
        document.body.appendChild(textarea);
        textarea.select();
        try {
          document.execCommand('copy');
          alert('HTML Copiado!!');
        } catch (err) {
          console.error('Erro ao copiar: ', err);
        }
        document.body.removeChild(textarea);
      }
  },
},
  computed :{
    generateHtml(){
      return ` <table class="row row-2" align="center" width="100%" border="0" cellpadding="0" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0;background-color:#fff"><tbody><tr><td><table class="row-content stack" align="center" border="0" cellpadding="0" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0;background-color:#fff;color:#000;width:510px;margin:0 auto" width="510"><tbody><tr><td class="column column-1" width="33.333333333333336%" style="mso-table-lspace:0;mso-table-rspace:0;font-weight:400;text-align:left;padding-bottom:5px;padding-top:5px;vertical-align:top;border-top:0;border-right:0;border-bottom:0;border-left:0"><table class="empty_block block-1" width="100%" border="0" cellpadding="0" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0"><tbody><tr><td class="pad"><div></div></td></tr></tbody></table></td><td class="column column-2" width="33.333333333333336%" style="mso-table-lspace:0;mso-table-rspace:0;font-weight:400;text-align:left;padding-bottom:5px;padding-top:5px;vertical-align:top;border-top:0;border-right:0;border-bottom:0;border-left:0"><table class="image_block block-1" width="100%" border="0" cellpadding="0" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0"><tbody><tr><td class="pad" style="width:100%"><div class="alignment" align="center" style="line-height:10px"><div style="max-width:59px">
        <a href="https://e.allin.b2bliz.com.br/bendar/?atmca=11419837&amp;atmme=1387&amp;atmte=1&amp;atmso=ck&amp;utm_content=293064835&amp;atmem=ZWxhaW5lQGVsYWluZWZubi5jb20uYnI=" target="_blank" style="outline:none; margin: 16px 0px;" tabindex="-1"><img style="margin: 12px 0px;" src="http://img.allin.mkt-allin.com.br/imeditor/beefree/images/ecdab2b9b380dd711b6b20aa90364dcc/liz-logo-email-1632324627284.png" style="display:block;height:auto;border:0;width:100%" width="59" height="auto"></a></div></div></td></tr></tbody></table></td><td class="column column-3" width="33.333333333333336%" style="mso-table-lspace:0;mso-table-rspace:0;font-weight:400;text-align:left;padding-bottom:5px;padding-top:5px;vertical-align:top;border-top:0;border-right:0;border-bottom:0;border-left:0"><table class="empty_block block-1" width="100%" border="0" cellpadding="0" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0"><tbody><tr><td class="pad"><div></div></td></tr></tbody></table></td></tr></tbody></table></td></tr></tbody></table>
        <div style="text-align: center; width: 100%;">
            <table style="margin: 0 auto; max-width: 530px; width: 100%; padding: 8px 0px; font-family: Arial, sans-serif; cursor: pointer; border-collapse: collapse;">
              <tbody>
              <tr>
                    <td style="padding: 0 10px;"><b><a target="_blank" style="color:black; font-weight:bold;" href="https://b2bliz.com.br/entrar">Novidades</a></b></td>
                    <td style="padding: 0 10px;"><a target="_blank" style="color:black" href="https://b2bliz.com.br/entrar">Lingeries</a></td>
                    <td style="padding: 0 10px;"><a target="_blank" style="color:black" href="https://b2bliz.com.br/entrar">Roupas</a></td>
                    <td style="padding: 0 10px;"><a target="_blank" style="color:black" href="https://b2bliz.com.br/entrar">Moda Praia</a></td>
                </tr>
              </tbody>  
            </table>
        </div>
            <hr class="pad" style="  color:lightgrey; margin: 12px 35%; text-align: center;">
        <!-- Área para colar o conteúdo textual do e-mail -->

        <div style="width: 100%; text-align: center; font-family: Arial, Helvetica Neue, Helvetica, sans-serif;">
          
          <table style="text-align:start; margin: 0 auto; max-width: 530px; width: 100%; border-collapse: collapse;">
                <tbody>
                    <tr>
                        <td>
                          <p>
                            <td><p>
                      <p>Olá, <b>${this.razaoSocial}</b>, temos uma notícia incrível para você!</p>
<p>Estamos felizes em anunciar que seu acesso exclusivo ao nosso portal b2bliz.com.br está liberado! Agora, você pode explorar todas as informações sobre a Liz e conhecer mais sobre nossa marca e produtos em um único local.</p>
 
<p>O que você encontrará no portal:</p>
<ul>
<li> Books Completos: Informações atualizadas de produtos e lançamentos.</li>
<li> Facilidade de Pedido: Faça seus pedidos de forma rápida e prática, diretamente pelo portal. Crie listas de desejos e receba uma cópia do pedido via e-mail com todas as imagens compradas.</li>
<li> Minha Conta: Resumo dos seus dados, pedidos e sugestões feitas pelo representante. Aqui você também tem a opção de alterar a senha de acesso.</li>
<li> Imagens Still: Clique com o botão direito sobre as imagens e baixe-as com facilidade.</li>
<li> Link para Downloads: Acesse imagens, books e vídeos de forma prática.</li>
<li> Interatividade com seu representante: Todo o trabalho online é compartilhado. Solicite um atendimento assistido e agende uma sala de atendimento.</li>
</ul>
                    </p></td>
                            </p>
                          </td>
                      </tr>
                  </tbody>
              </table>
            <table style="margin: 0 auto; max-width: 530px; width: 100%; border-collapse: collapse;">
              <tbody>     
                <tr>
                  
                    <td style="padding: 8px;">
                        <div style="margin: 0; text-align:start;">
                            <p>Utilize os seguintes dados para acessar a loja.</p>
                            <p><p>CNPJ:  <b>${this.cnpj}</b> </p>
                            <p>SENHA:  <b>${this.senha}</b> </p>
                            <p>Sugerimos alterar a senha no <a target="_blank" href="https://b2bliz.com.br/entrar">site</a> assim que possível.</p>
                            <p>Atenciosamente,</p>
                            <p>Equipe Liz.</p>
                            <p>E-mail Externo: Não clique em links ou abra anexos, a menos que conheça o remetente e tenha certeza do conteúdo.</p>
                        </div>
                    </td>
                </tr>
              </tbody>
            </table>

        </div>
    <table class="row row-4" align="center" width="100%" border="0" cellpadding="0" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0;background-color:#fff"><tbody><tr><td><table class="row-content stack" align="center" border="0" cellpadding="0" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0;background-color:#fff;color:#000;width:510px;margin:0 auto" width="510"><tbody><tr>
<td class="column column-1" width="100%" style="mso-table-lspace:0;mso-table-rspace:0;font-weight:400;text-align:left;vertical-align:top;border-top:0;border-right:0;border-bottom:0;border-left:0"><table class="image_block block-1" width="100%" border="0" cellpadding="0" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0"><tbody><tr><td class="pad" style="padding-top:10px;width:100%"><div class="alignment" align="center" style="line-height:10px"><div style="max-width:530px"><a href="https://e.allin.b2bliz.com.br/bendar/?atmca=11419837&amp;atmme=1387&amp;atmte=1&amp;atmso=ck&amp;utm_content=293064835&amp;atmem=ZWxhaW5lQGVsYWluZWZubi5jb20uYnI=" target="_blank" style="outline:none" tabindex="-1"><img src="http://img.allin.mkt-allin.com.br/imeditor/beefree/images/ecdab2b9b380dd711b6b20aa90364dcc/2022_03_08_conhece_a_liz-3-1646666702768.png" style="display:block;height:auto;border:0;" width="530" height="auto"></a></div></div></td></tr></tbody></table></td></tr></tbody></table></td></tr></tbody></table>
<table class="row row-5" align="center" width="100%" border="0" cellpadding="0" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0;background-color:#fff"><tbody><tr><td><table class="row-content stack" align="center" border="0" cellpadding="0" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0;background-color:#f9f9f9;color:#000;width:510px;margin:0 auto" width="510"><tbody><tr><td class="column column-1" width="100%" style="mso-table-lspace:0;mso-table-rspace:0;font-weight:400;text-align:left;padding-bottom:5px;vertical-align:top;border-top:0;border-right:0;border-bottom:0;border-left:0"><table class="divider_block block-1" width="100%" border="0" cellpadding="10" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0"><tbody><tr><td class="pad"><div class="alignment" align="center"><table border="0" cellpadding="0" cellspacing="0" role="presentation" width="100%" style="mso-table-lspace:0;mso-table-rspace:0"><tbody><tr><td class="divider_inner" style="font-size:1px;line-height:1px;border-top:1px solid #bbb"><span style="word-break: break-word;"> </span></td></tr></tbody></table></div></td></tr></tbody></table><table class="social_block block-2" width="100%" border="0" cellpadding="10" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0"><tbody><tr><td class="pad"><div class="alignment" align="center">
    <table class="social_block block-1" width="100%" border="0" cellpadding="0" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0"> 
        <tbody> 
         <tr> 
          <td class="pad" style="text-align:center"> 
           <div class="alignment" style="text-align:center; padding: 8px 0px;"> 
            <table class="social-table" width="276px" border="0" cellpadding="0" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0;display:inline-block"> 
             <tbody> 
              <tr> 
               <td style="padding:0 7px 0 7px"><a href="http://e.allin.news.liz.com.br/transactional/click/c3a547efac3b8c4bb51f2a477c46ca6a/eyJyZWNlaXZlciI6ICJlbGFpbmVAZWxhaW5lZm5uLmNvbS5iciIsICJjaGFubmVsIjogIkVNQUlMIiwgIm1lc3NhZ2VJZCI6ICIwODRjOWEyMi04OTdiLTQxNTctYTViYi1lNmYwYjM3OTg3NmIiLCAiY3VzdG9tZXJJZCI6ICI5OTcwIiwgImV4dGVybmFsSWQiOiAiQlRHLTE2MDQiLCAibGluayI6ICJodHRwczovL3d3dy5mYWNlYm9vay5jb20vTGl6TGluZ2VyaWUvP3V0bV9zb3VyY2U9QlRHMzYwJnV0bV9tZWRpdW09ZW1haWwmdXRtX2NhbXBhaWduXHQ9TmF2ZWdhY2FvX1NlbWFuYWwifQ==?key=b88758c2-a532-4616-8e5a-04cb77d3a61c" target="_blank"><img src="https://app-rsrc.getbee.io/public/resources/social-networks-icon-sets/t-outline-circle-dark-gray/facebook@2x.png" width="32" height="32" alt="Facebook" title="Facebook" style="display:block;height:auto;border:0"></a></td> 
               <td style="padding:0 7px 0 7px"><a href="http://e.allin.news.liz.com.br/transactional/click/53549a2ea4d40c94c923a95284d944e8/eyJyZWNlaXZlciI6ICJlbGFpbmVAZWxhaW5lZm5uLmNvbS5iciIsICJjaGFubmVsIjogIkVNQUlMIiwgIm1lc3NhZ2VJZCI6ICIwODRjOWEyMi04OTdiLTQxNTctYTViYi1lNmYwYjM3OTg3NmIiLCAiY3VzdG9tZXJJZCI6ICI5OTcwIiwgImV4dGVybmFsSWQiOiAiQlRHLTE2MDQiLCAibGluayI6ICJodHRwczovL3d3dy5pbnN0YWdyYW0uY29tL2xpemxpbmdlcmllLz91dG1fc291cmNlPUJURzM2MCZ1dG1fbWVkaXVtPWVtYWlsJnV0bV9jYW1wYWlnblx0PU5hdmVnYWNhb19TZW1hbmFsIn0=?key=a3214b90-c8c9-41bc-b588-9f5cb8e6767f" target="_blank"><img src="https://app-rsrc.getbee.io/public/resources/social-networks-icon-sets/t-outline-circle-dark-gray/instagram@2x.png" width="32" height="32" alt="Instagram" title="Instagram" style="display:block;height:auto;border:0"></a></td> 
               <td style="padding:0 7px 0 7px"><a href="http://e.allin.news.liz.com.br/transactional/click/7f289e646a3e0f6a7808a2f0ac17e5a2/eyJyZWNlaXZlciI6ICJlbGFpbmVAZWxhaW5lZm5uLmNvbS5iciIsICJjaGFubmVsIjogIkVNQUlMIiwgIm1lc3NhZ2VJZCI6ICIwODRjOWEyMi04OTdiLTQxNTctYTViYi1lNmYwYjM3OTg3NmIiLCAiY3VzdG9tZXJJZCI6ICI5OTcwIiwgImV4dGVybmFsSWQiOiAiQlRHLTE2MDQiLCAibGluayI6ICJodHRwczovL3B0LmxpbmtlZGluLmNvbS9jb21wYW55L2xpemxpbmdlcmllP3V0bV9zb3VyY2U9QlRHMzYwJnV0bV9tZWRpdW09ZW1haWwmdXRtX2NhbXBhaWduXHQ9TmF2ZWdhY2FvX1NlbWFuYWwifQ==?key=8de97965-b9f7-4c44-be1f-63c7984a485a" target="_blank"><img src="https://app-rsrc.getbee.io/public/resources/social-networks-icon-sets/t-outline-circle-dark-gray/linkedin@2x.png" width="32" height="32" alt="LinkedIn" title="LinkedIn" style="display:block;height:auto;border:0"></a></td> 
               <td style="padding:0 7px 0 7px"><a href="http://e.allin.news.liz.com.br/transactional/click/5eba0d036f714b909f439b27a3acd98d/eyJyZWNlaXZlciI6ICJlbGFpbmVAZWxhaW5lZm5uLmNvbS5iciIsICJjaGFubmVsIjogIkVNQUlMIiwgIm1lc3NhZ2VJZCI6ICIwODRjOWEyMi04OTdiLTQxNTctYTViYi1lNmYwYjM3OTg3NmIiLCAiY3VzdG9tZXJJZCI6ICI5OTcwIiwgImV4dGVybmFsSWQiOiAiQlRHLTE2MDQiLCAibGluayI6ICJodHRwczovL3d3dy55b3V0dWJlLmNvbS9jL2xpemxpbmdlcmllb2ZpY2lhbD91dG1fc291cmNlPUJURzM2MCZ1dG1fbWVkaXVtPWVtYWlsJnV0bV9jYW1wYWlnblx0PU5hdmVnYWNhb19TZW1hbmFsIn0=?key=38599ee1-a13b-463b-8892-549819f76e03" target="_blank"><img src="https://app-rsrc.getbee.io/public/resources/social-networks-icon-sets/t-outline-circle-dark-gray/youtube@2x.png" width="32" height="32" alt="YouTube" title="YouTube" style="display:block;height:auto;border:0"></a></td> 
               <td style="padding:0 7px 0 7px"><a href="http://e.allin.news.liz.com.br/transactional/click/9adeea42c09689521f39b036b1b3dcf7/eyJyZWNlaXZlciI6ICJlbGFpbmVAZWxhaW5lZm5uLmNvbS5iciIsICJjaGFubmVsIjogIkVNQUlMIiwgIm1lc3NhZ2VJZCI6ICIwODRjOWEyMi04OTdiLTQxNTctYTViYi1lNmYwYjM3OTg3NmIiLCAiY3VzdG9tZXJJZCI6ICI5OTcwIiwgImV4dGVybmFsSWQiOiAiQlRHLTE2MDQiLCAibGluayI6ICJodHRwczovL2JyLnBpbnRlcmVzdC5jb20vbGl6X2xpbmdlcmllLyA/dXRtX3NvdXJjZT1CVEczNjAmdXRtX21lZGl1bT1lbWFpbCZ1dG1fY2FtcGFpZ25cdD1OYXZlZ2FjYW9fU2VtYW5hbCJ9?key=652d4c1c-88b8-4c79-a348-c20a8ebcbf8e" target="_blank"><img src="https://app-rsrc.getbee.io/public/resources/social-networks-icon-sets/t-outline-circle-dark-gray/pinterest@2x.png" width="32" height="32" alt="Pinterest" title="Pinterest" style="display:block;height:auto;border:0"></a></td> 
               <td style="padding:0 7px 0 7px"><a href="http://e.allin.news.liz.com.br/transactional/click/9c4aec86c5388777fccda0a3ae37556b/eyJyZWNlaXZlciI6ICJlbGFpbmVAZWxhaW5lZm5uLmNvbS5iciIsICJjaGFubmVsIjogIkVNQUlMIiwgIm1lc3NhZ2VJZCI6ICIwODRjOWEyMi04OTdiLTQxNTctYTViYi1lNmYwYjM3OTg3NmIiLCAiY3VzdG9tZXJJZCI6ICI5OTcwIiwgImV4dGVybmFsSWQiOiAiQlRHLTE2MDQiLCAibGluayI6ICJodHRwczovL3d3dy50aWt0b2suY29tL0BsaXpsaW5nZXJpZT91dG1fc291cmNlPUJURzM2MCZ1dG1fbWVkaXVtPWVtYWlsJnV0bV9jYW1wYWlnblx0PU5hdmVnYWNhb19TZW1hbmFsIn0=?key=4fd43c48-9a4e-4a59-8c80-1b56c0fbb2fd" target="_blank"><img src="https://app-rsrc.getbee.io/public/resources/social-networks-icon-sets/t-outline-circle-dark-gray/tiktok@2x.png" width="32" height="32" alt="TikTok" title="TikTok" style="display:block;height:auto;border:0"></a></td> 
              </tr> 
             </tbody> 
            </table> 
           </div></td> 
         </tr> 
        </tbody> 
       </table>
<table class="row row-6" align="center" width="100%" border="0" cellpadding="0" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0;background-color:#fff">
    <tbody>
        <tr>
            <td>
                <table class="row-content stack" align="center" border="0" cellpadding="0" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0;background-color:#eee;color:#000;width:510px;margin:0 auto" width="510">
                    <tbody>
                        <tr>
                            <td class="column column-1" width="100%" style="mso-table-lspace:0;mso-table-rspace:0;font-weight:400;text-align:left;padding-bottom:5px;padding-top:5px;vertical-align:top;border-top:0;border-right:0;border-bottom:0;border-left:0">
                                <table class="text_block block-1" width="100%" border="0" cellpadding="10" cellspacing="0" role="presentation" style="mso-table-lspace:0;mso-table-rspace:0;word-break:break-word">
                                    <tbody>
                                        <tr>
                                            <td class="pad"><div style="font-family:sans-serif">
                                                <div class="" style="font-size:14px;font-family:Arial,Helvetica Neue,Helvetica,sans-serif;mso-line-height-alt:16.8px;color:#555;line-height:1.2">
                                                    <p style="margin:0;font-size:12px;mso-line-height-alt:14.399999999999999px"><strong><span style="word-break: break-word; font-size: 18px;">Entre em contato conosco através do SAC Liz: </span></strong></p>
                                                    <p style="margin:0;font-size:12px;mso-line-height-alt:16.8px">&nbsp;</p>
                                                    <p style="margin:0;font-size:12px;mso-line-height-alt:14.399999999999999px"><span style="word-break: break-word; font-size: 14px;"><b>Horário de atendimento:</b>De segunda a sexta das 8h às 16h (exceto feriados) </span></p>
                                                    <p style="margin:0;font-size:12px;mso-line-height-alt:16.8px">&nbsp;</p><p style="margin:0;font-size:16px;mso-line-height-alt:14.399999999999999px"><strong><span style="word-break: break-word; font-size: 14px;"><b>Telefone:</b> <a href="tel:+551145893514" style="color:#ff6900">(11) 4589-3514</a></span></strong></p>
                                                    <p style="margin:0;font-size:12px;mso-line-height-alt:16.8px">&nbsp;</p><p style="margin:0;font-size:16px;mso-line-height-alt:14.399999999999999px"><span style="word-break: break-word; color: #ff6900; font-size: 14px;"><a href="mailto:saclizbusiness@cmrcia.com.br?subject=saclizbusiness@cmrcia.com.br" target="_blank" title="saclizbusiness@cmrcia.com.br"  style="text-decoration: none;" rel="noopener"><span style="word-break: break-word; color: #ff6900; "><b style="color:black;">E-mail: </b>saclizbusiness@cmrcia.com.br</span></a></span></p>
                                                    <p style="margin:0;font-size:16px;mso-line-height-alt:16.8px">&nbsp;</p><p style="margin:0;font-size:16px;mso-line-height-alt:16.8px">&nbsp;</p><p style="margin:0;font-size:10px;mso-line-height-alt:16.8px">&nbsp;</p>
                                                    <p style="margin:0;font-size:16px;mso-line-height-alt:14.399999999999999px"><strong><span style="word-break: break-word; font-size: 18px;">Informações Gerais:</span></strong></p>
                                                    <p style="margin:0;font-size:16px;mso-line-height-alt:16.8px">&nbsp;</p><p style="margin:0;font-size:16px;mso-line-height-alt:14.399999999999999px"><span style="word-break: break-word; font-size: 14px;">Para receber nossa newsletter insira o e-mail <span style="word-break: break-word; color: #ff6900;"><a href="mailto:postmaster@lizbusiness.com.br?subject=postmaster@lizbusiness.com.br" target="_blank" title="postmaster@lizbusiness.com.br" style="text-decoration:underline;color:#ff6900;" rel="noopener">postmaster@lizbusiness.com.br</a></span> em sua lista de rementes confiáveis. </span></p>
                                                    <p style="margin:0;font-size:16px;mso-line-height-alt:16.8px">&nbsp;</p><p style="margin:0;font-size:16px;mso-line-height-alt:16.8px">&nbsp;</p>
                                                    <p style="margin:0;font-size:16px;mso-line-height-alt:14.399999999999999px"><span style="word-break: break-word; font-size: 14px;">Condições válidas enquanto durarem os estoques, sujeitas a alterações sem aviso prévio. No caso de promoções, confira os regulamentos no site Regulamento de Promoção. Consulte o site para maiores detalhes dos produtos anunciados. Caso haja divergência na descrição do produto ou de preço entre este e-mail e o site, a condição válida será a do site. Todas as imagens deste e-mail são meramente ilustrativas. </span></p>
                                                    <p style="margin:0;font-size:16px;mso-line-height-alt:16.8px">&nbsp;</p><p style="margin:0;font-size:16px;mso-line-height-alt:16.8px">&nbsp;</p>
                                                    <p style="margin:0;font-size:16px;mso-line-height-alt:16.8px">&nbsp;</p>
                                                    <p style="margin:0;font-size:16px;mso-line-height-alt:14.399999999999999px"><strong><span style="word-break: break-word; font-size: 18px;">Nosso Endereço:</span></strong></p>
                                                    <p style="margin:0;font-size:16px;mso-line-height-alt:16.8px">&nbsp;</p>
                                                    <p style="margin:0;font-size:16px;mso-line-height-alt:14.399999999999999px"><span style="word-break: break-word; font-size: 14px;">CMR Indústria e Comercio LTDA Av. Antonieta Piva Barranqueiros, 2000 - Distrito Industrial - Jundiaí - SP</span></p>
                                                </div></div></td></tr></tbody></table></td></tr></tbody></table></td></tr></tbody>
                                            </table>` 
    },
    escapedHtml() {
      return this.generateHtml
        
    }
  }
}

</script>

<style>

</style>

