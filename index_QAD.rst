SPID Quality Assessment Document – Authentication RP

Checklist per la verifica dell’implementazione dell’ Authorization
Request degli OIDC Relying Party SPID

Il presente documento contiene l’elenco dei test generali che permettono
di valutare il livello di conformità dell’implementazione di un OIDC
Relying Party alle regole tecniche SPID OIDC e successivi avvisi. I test
di seguito indicati sono gli stessi eseguiti da AgID per la verifica
tecnica dell’implementazione. Il documento vuole essere uno strumento
utile ai fornitori di servizi per effettuare i necessari test di
conformità prima di richiedere la verifica tecnica ad AgID.

+------------------+--------------+
| Data: 23/09/2022 | Versione 1.1 |
+------------------+--------------+

**Version History**

+------------------+--------+-------+-----------+
| Versione         | Autore | Stato | Modifiche |
+==================+========+=======+===========+
| 1.0 (05/09/2022) | AgID   | Bozza |           |
+------------------+--------+-------+-----------+
| 1.1 (23/09/2022) | AgID   | Bozza | Revisione |
+------------------+--------+-------+-----------+
|                  |        |       |           |
+------------------+--------+-------+-----------+

**Referements**

+-----------------------+-----------------------+-----------------------+
| Ref                   | Document              | Link                  |
+=======================+=======================+=======================+
| OIDC_CORE             | OpenID Connect Core   | https://openid.net/sp |
|                       | Discovery             | ecs/openid-connect-di |
|                       |                       | scovery-1_0.html      |
+-----------------------+-----------------------+-----------------------+
| OIDC_FED              | OpenID Connect        | https://openid.net/sp |
|                       | Federation            | ecs/openid-connect-fe |
|                       |                       | deration-1_0.html     |
+-----------------------+-----------------------+-----------------------+
| OIDC_SPID             | LL. GG. OpenID        | https://www.agid.gov. |
|                       | Connect in SPID       | it/sites/default/file |
|                       |                       | s/repository_files/li |
|                       |                       | nee_guida_openid_conn |
|                       |                       | ect_in_spid.pdf       |
+-----------------------+-----------------------+-----------------------+
| SPID_A41              | Avviso SPID N. 41     | https://www.agid.gov. |
|                       |                       | it/sites/default/file |
|                       |                       | s/repository_files/sp |
|                       |                       | id-avviso-n41-integra |
|                       |                       | zione_ll.gg_._openid_ |
|                       |                       | connect_in_spid.pdf   |
+-----------------------+-----------------------+-----------------------+
| AGID_PKI              | PKI AgID              |                       |
+-----------------------+-----------------------+-----------------------+
| SPID_AA               | LL. GG. Attribute     | https://www.agid.gov. |
|                       | Authority             | it/sites/default/file |
|                       |                       | s/repository_files/ll |
|                       |                       | gg_attribute_authorit |
|                       |                       | y-allegato_tecnico_oa |
|                       |                       | s3.pdf                |
+-----------------------+-----------------------+-----------------------+

Test sulla correttezza della Richiesta di Autenticazione

Check the Authentication Request

+-----------------+-----------------+-----------------+-----------------+
| Num             | Ref             | Descrizione     | Esito           |
+=================+=================+=================+=================+
| 2.0.0           | OIDC_SPID       | the request     |                 |
|                 |                 | MUST be sent on |                 |
|                 |                 | HTTP method GET |                 |
|                 |                 | or POST         |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.1           | OIDC_SPID       | the parameter   |                 |
|                 |                 | request MUST be |                 |
|                 |                 | present         |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.2           | OIDC_SPID       | the value of    |                 |
|                 |                 | request MUST be |                 |
|                 |                 | a valid JWT     |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.3           | OIDC_SPID       | the signature   |                 |
|                 |                 | of request JWT  |                 |
|                 |                 | MUST be valid   |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.4           | OIDC_SPID       | the parameter   |                 |
|                 |                 | client_id MUST  |                 |
|                 |                 | be present as   |                 |
|                 |                 | HTTP parameter  |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.5           | OIDC_SPID       | the parameter   |                 |
|                 |                 | client_id MUST  |                 |
|                 |                 | be present into |                 |
|                 |                 | request JWT     |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.6           | OIDC_SPID       | the values of   |                 |
|                 |                 | client_id MUST  |                 |
|                 |                 | be the same     |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.7           | OIDC_SPID       | the value of    |                 |
|                 |                 | client_id MUST  |                 |
|                 |                 | be trusted      |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.8           | OIDC_SPID       | the parameter   |                 |
|                 |                 | response_type   |                 |
|                 |                 | MUST be present |                 |
|                 |                 | as HTTP         |                 |
|                 |                 | parameter       |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.9           | OIDC_SPID       | the parameter   |                 |
|                 |                 | response_type   |                 |
|                 |                 | MUST be present |                 |
|                 |                 | into request    |                 |
|                 |                 | JWT             |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.10          | OIDC_SPID       | the values of   |                 |
|                 |                 | response_type   |                 |
|                 |                 | MUST be the     |                 |
|                 |                 | same            |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.11          | OIDC_SPID       | the value of    |                 |
|                 |                 | response_type   |                 |
|                 |                 | MUST be 'code'  |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.12          | OIDC_SPID       | the parameter   |                 |
|                 |                 | scope MUST be   |                 |
|                 |                 | present as HTTP |                 |
|                 |                 | parameter       |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.13          | OIDC_SPID       | the parameter   |                 |
|                 |                 | scope MUST be   |                 |
|                 |                 | present into    |                 |
|                 |                 | request JWT     |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.14          | OIDC_SPID       | the values of   |                 |
|                 |                 | scope MUST be   |                 |
|                 |                 | the same        |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.15          | OIDC_SPID       | the value of    |                 |
|                 |                 | scope MUST      |                 |
|                 |                 | contain         |                 |
|                 |                 | 'openid'        |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.16          | OIDC_SPID       | the parameter   |                 |
|                 |                 | code_challenge  |                 |
|                 |                 | MUST be present |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.17          | OIDC_SPID       | the parameter   |                 |
|                 |                 | code_challenge_ |                 |
|                 |                 | method          |                 |
|                 |                 | MUST be present |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.18          | OIDC_SPID       | the value of    |                 |
|                 |                 | code_challenge_ |                 |
|                 |                 | method          |                 |
|                 |                 | MUST be 'S256'  |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.19          | OIDC_SPID       | the parameter   |                 |
|                 |                 | nonce MUST be   |                 |
|                 |                 | present         |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.20          | OIDC_SPID       | the length of   |                 |
|                 |                 | value of nonce  |                 |
|                 |                 | MUST be >= 32   |                 |
|                 |                 | chars           |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.21          | OIDC_SPID       | the parameter   |                 |
|                 |                 | prompt MUST be  |                 |
|                 |                 | present         |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.22          | OIDC_SPID       | the value of    |                 |
|                 | SPID_A41        | prompt MUST be  |                 |
|                 |                 | one of          |                 |
|                 |                 | ['consent',     |                 |
|                 |                 | 'consent_login' |                 |
|                 |                 | ] [3]_          |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.23          | OIDC_SPID       | the parameter   |                 |
|                 |                 | redirect_uri    |                 |
|                 |                 | MUST be present |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.24          | OIDC_SPID       | the value of    |                 |
|                 |                 | redirect_uri    |                 |
|                 |                 | MUST be trusted |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.25          | OIDC_SPID       | the parameter   |                 |
|                 |                 | acr_values MUST |                 |
|                 |                 | be present      |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.26          | OIDC_SPID       | the values of   |                 |
|                 |                 | acr_values MUST |                 |
|                 |                 | be in           |                 |
|                 |                 | ['https://www.s |                 |
|                 |                 | pid.gov.it/Spid |                 |
|                 |                 | L1',            |                 |
|                 |                 | 'https://www.sp |                 |
|                 |                 | id.gov.it/SpidL |                 |
|                 |                 | 2',             |                 |
|                 |                 | 'https://www.sp |                 |
|                 |                 | id.gov.it/SpidL |                 |
|                 |                 | 3']             |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.27          | OIDC_SPID       | the parameter   |                 |
|                 |                 | claims MUST be  |                 |
|                 |                 | present         |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.28          | OIDC_SPID       | the value of    |                 |
|                 |                 | claims MUST be  |                 |
|                 |                 | as expected     |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.29          | OIDC_SPID       | the claims MUST |                 |
|                 |                 | be requested    |                 |
|                 |                 | into id_token   |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.30          | OIDC_SPID       | the requested   |                 |
|                 |                 | claims MUST be  |                 |
|                 |                 | valid [4]_      |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.31          | OIDC_SPID       | the parameter   |                 |
|                 |                 | state MUST be   |                 |
|                 |                 | present         |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.0.32          | OIDC_SPID       | the length of   |                 |
|                 |                 | state value     |                 |
|                 |                 | MUST be >= 32   |                 |
|                 |                 | chars           |                 |
+-----------------+-----------------+-----------------+-----------------+

Check the Authentication Request for offline_access

+-----------------+-----------------+-----------------+-----------------+
| Num             | Ref             | Descrizione     | Esito           |
+=================+=================+=================+=================+
| 2.1.0           | OIDC_SPID       | the value of    |                 |
|                 |                 | scope MUST      |                 |
|                 |                 | contain         |                 |
|                 |                 | 'offline_access |                 |
|                 |                 | '               |                 |
+-----------------+-----------------+-----------------+-----------------+
| 2.1.1           | OIDC_SPID       | the value of    |                 |
|                 |                 | acr_values MUST |                 |
|                 |                 | contain         |                 |
|                 |                 | 'https://www.sp |                 |
|                 |                 | id.gov.it/SpidL |                 |
|                 |                 | 1'              |                 |
+-----------------+-----------------+-----------------+-----------------+

Check the Authentication Successful Response

+-------------+-------------+-------------+-------------+-------------+
| Num         | Ref         | Descrizione | Atteso      | Esito       |
+=============+=============+=============+=============+=============+
| 2.2.0       | OIDC_SPID   | parameter   | generic     |             |
|             |             | code is not | error       |             |
|             |             | present     |             |             |
+-------------+-------------+-------------+-------------+-------------+
| 2.2.1       | OIDC_SPID   | parameter   | generic     |             |
|             |             | state is    | error       |             |
|             |             | not present |             |             |
+-------------+-------------+-------------+-------------+-------------+
| 2.2.2       | OIDC_SPID   | the value   | generic     |             |
|             |             | of state is | error       |             |
|             |             | different   |             |             |
|             |             | from the    |             |             |
|             |             | value of    |             |             |
|             |             | state sent  |             |             |
|             |             | with the    |             |             |
|             |             | authorizati |             |             |
|             |             | on          |             |             |
|             |             | request     |             |             |
+-------------+-------------+-------------+-------------+-------------+
| 2.2.3       | SPID_A41    | the value   | generic     |             |
|             |             | of code is  | error       |             |
|             |             | not UUID    |             |             |
+-------------+-------------+-------------+-------------+-------------+

Check the Authentication Error Response

+-------------+-------------+-------------+-------------+-------------+
| Num         | Ref         | Descrizione | Atteso      | Esito       |
+=============+=============+=============+=============+=============+
| 2.3.0       | OIDC_SPID   | parameter   | generic     |             |
|             |             | error is    | error       |             |
|             |             | not present |             |             |
+-------------+-------------+-------------+-------------+-------------+
| 2.3.1       | OIDC_SPID   | the value   | generic     |             |
|             |             | of error is | error       |             |
|             |             | different   |             |             |
|             |             | from        |             |             |
|             |             | ['access_de |             |             |
|             |             | nied',      |             |             |
|             |             | 'invalid_cl |             |             |
|             |             | ient',      |             |             |
|             |             | 'invalid_re |             |             |
|             |             | quest',     |             |             |
|             |             | 'invalid_sc |             |             |
|             |             | ope',       |             |             |
|             |             | 'server_err |             |             |
|             |             | or',        |             |             |
|             |             | 'temporary_ |             |             |
|             |             | unavailable |             |             |
|             |             | ']          |             |             |
+-------------+-------------+-------------+-------------+-------------+
| 2.3.2       | OIDC_SPID   | parameter   | generic     |             |
|             |             | error_descr | error       |             |
|             |             | iption      |             |             |
|             |             | is not      |             |             |
|             |             | present     |             |             |
+-------------+-------------+-------------+-------------+-------------+
| 2.3.3       | OIDC_SPID   | parameter   | generic     |             |
|             |             | state is    | error       |             |
|             |             | not present |             |             |
+-------------+-------------+-------------+-------------+-------------+
| 2.3.4       | OIDC_SPID   | the value   | generic     |             |
|             |             | of state is | error       |             |
|             |             | different   |             |             |
|             |             | from the    |             |             |
|             |             | value of    |             |             |
|             |             | state sent  |             |             |
|             |             | with the    |             |             |
|             |             | authorizati |             |             |
|             |             | on          |             |             |
|             |             | request     |             |             |
+-------------+-------------+-------------+-------------+-------------+
| 2.3.5       | SPID_A41    | the value   | show an     |             |
|             |             | of error is | error page  |             |
|             |             | 'access_den | to user as  |             |
|             |             | ied'        | expected by |             |
|             |             |             | SPID Notice |             |
|             |             |             | n. 41       |             |
+-------------+-------------+-------------+-------------+-------------+
| 2.3.6       | SPID_A41    | the value   | show an     |             |
|             |             | of error is | error page  |             |
|             |             | 'invalid_cl | to user as  |             |
|             |             | ient'       | expected by |             |
|             |             |             | SPID Notice |             |
|             |             |             | n. 41       |             |
+-------------+-------------+-------------+-------------+-------------+
| 2.3.7       | SPID_A41    | the value   | show an     |             |
|             |             | of error is | error page  |             |
|             |             | 'invalid_re | to user as  |             |
|             |             | quest'      | expected by |             |
|             |             |             | SPID Notice |             |
|             |             |             | n. 41       |             |
+-------------+-------------+-------------+-------------+-------------+
| 2.3.8       | SPID_A41    | the value   | show an     |             |
|             |             | of error is | error page  |             |
|             |             | 'invalid_sc | to user as  |             |
|             |             | ope'        | expected by |             |
|             |             |             | SPID Notice |             |
|             |             |             | n. 41       |             |
+-------------+-------------+-------------+-------------+-------------+
| 2.3.9       | SPID_A41    | the value   | show an     |             |
|             |             | of error is | error page  |             |
|             |             | 'server_err | to user as  |             |
|             |             | or'         | expected by |             |
|             |             |             | SPID Notice |             |
|             |             |             | n. 41       |             |
+-------------+-------------+-------------+-------------+-------------+
| 2.3.10      | SPID_A41    | the value   | show an     |             |
|             |             | of error is | error page  |             |
|             |             | 'temporaril | to user as  |             |
|             |             | y_unavailab | expected by |             |
|             |             | le'         | SPID Notice |             |
|             |             |             | n. 41       |             |
+-------------+-------------+-------------+-------------+-------------+

.. [1]
   L’implementazione del valore “verify” è sospesa fino a indicazione
   contraria di AGID [OIDC_A41]

.. [2]
   vedi tabella attributi SPID OIDC

.. [3]
   L’implementazione del valore “verify” è sospesa fino a indicazione
   contraria di AGID [OIDC_A41]

.. [4]
   vedi tabella attributi SPID OIDC
