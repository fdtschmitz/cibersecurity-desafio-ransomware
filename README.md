# Desafio Ransomware
>Este desafio faz parte do conteúdo abordado pelo *Santander Bootcamp Cibersegurança*, ministrado pela [DIO](https://web.dio.me/track/santander-bootcamp-ciberseguranca?tab=about).

## Características
* Criado utilizando Python
* Faz uso da biblioteca pyaes para encriptação
* Implementação de didática simples para entendimento dos conceitos.

## Funcionamento
### encrypter.py
1. Abertura do arquivo original: O código começa abrindo o arquivo "teste.txt" em modo de leitura binária ("rb"). O conteúdo do arquivo é lido e armazenado na variável file_data. Posteriormente, o arquivo original é fechado.

2. Remoção do arquivo original: O arquivo original ("teste.txt") é removido usando a função os.remove(file_name). Isso significa que, após a execução deste trecho de código, o arquivo original não existe mais no sistema de arquivos.

3. Chave de criptografia: Uma chave de criptografia key é definida como uma sequência de bytes (b"testeransomwares"). Em seguida, é criada uma instância da classe AESModeOfOperationCTR da biblioteca *pyaes* usando essa chave.

4. Criptografia do arquivo: O conteúdo do arquivo original (file_data) é criptografado usando a chave e o modo de operação CTR do AES. O resultado é armazenado na variável crypto_data.

5. Salvamento do arquivo criptografado: Um novo arquivo é criado com um nome composto pela adição da extensão ".ransomwaretroll" ao nome do arquivo original. Esse novo arquivo contém os dados criptografados.

Uma vez finalizado, o arquivo original deixa de existir, sendo substituido por uma versão encriptada. Para voltarmos à condição inicial utilizamos o decrypter.py.

---

### decrypter.py
1. Abertura do arquivo criptografado: O código começa abrindo um arquivo criptografado chamado "teste.txt.ransomwaretroll" em modo de leitura binária ("rb"). O conteúdo do arquivo criptografado é lido e armazenado na variável file_data. Posteriormente, o arquivo criptografado é fechado.

2. Chave para descriptografia: Uma chave de descriptografia key é definida como uma sequência de bytes (b"testeransomwares"). Em seguida, é criada uma instância da classe AESModeOfOperationCTR da biblioteca pyaes usando essa chave.

3. Descriptografia do arquivo: O conteúdo do arquivo criptografado (file_data) é descriptografado usando a chave e o modo de operação CTR do AES. O resultado é armazenado na variável decrypt_data.

4. Remoção do arquivo criptografado: O arquivo criptografado ("teste.txt.ransomwaretroll") é removido do sistema de arquivos usando a função os.remove(file_name).

5. Criação do arquivo descriptografado: Um novo arquivo é criado com o nome original ("teste.txt") contendo os dados descriptografados.

## Considerações Finais

Entender como um ataque desse tipo pode ocorrer é importante para implementar medidas preventivas e proteger sistemas contra possíveis ameaças. Vale ressaltar que este material possui fins educativos.

### Para realizar um ataque de ransomware:
1. Acesso ao Sistema: O atacante precisaria ter acesso ao sistema alvo. Isso pode ocorrer por meio de vulnerabilidades de segurança, phishing, engenharia social ou outros métodos de exploração.
2. Criptografia: Utilizando uma biblioteca de criptografia, como a pyaes no exemplo, o atacante criptografaria os arquivos da vítima. Normalmente, o ransomware usaria uma chave única para cada vítima ou um par de chaves pública/privada para tornar a descriptografia mais difícil.
3. Comunicação com o Atacante: O atacante forneceria um meio para a vítima entrar em contato, geralmente exigindo o pagamento de um resgate em criptomoedas para obter a chave de descriptografia.

### Para evitar um ataque de ransomware:
1. Backup Regular: Mantenha backups regulares dos seus dados em locais isolados. Isso pode permitir a recuperação dos dados sem precisar pagar um resgate.
2. Atualizações de Software: Mantenha o software do sistema operacional, antivírus e outras aplicações sempre atualizados para corrigir vulnerabilidades conhecidas.
3. Conscientização e Treinamento: Eduque os usuários sobre práticas seguras online, como evitar clicar em links suspeitos ou abrir anexos de e-mails desconhecidos.
4. Filtros de E-mail e Antivírus: Utilize filtros de e-mail eficientes para bloquear e-mails de phishing e empregue software antivírus para detectar possíveis ameaças.
5. Restrições de Privilégios: Limite as permissões de usuário para impedir que malware se propague facilmente pelo sistema.
6. Firewalls: Configure firewalls para bloquear tráfego suspeito e proteger contra invasões.
7. Monitoramento de Rede: Implemente ferramentas de monitoramento de rede para identificar padrões de tráfego suspeitos.
8. Desconfiança de Anexos e Links: Incentive a desconfiança em relação a anexos de e-mail e links, mesmo quando parecem legítimos. Lembre-se, a prevenção é a chave. Manter uma postura proativa em relação à segurança cibernética e estar ciente das melhores práticas são formas eficazes de evitar ataques de ransomware e outras ameaças.
