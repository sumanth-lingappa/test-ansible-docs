
.. Document meta

:orphan:

.. |antsibull-internal-nbsp| unicode:: 0xA0
    :trim:

.. role:: ansible-attribute-support-label
.. role:: ansible-attribute-support-property
.. role:: ansible-attribute-support-full
.. role:: ansible-attribute-support-partial
.. role:: ansible-attribute-support-none
.. role:: ansible-attribute-support-na
.. role:: ansible-option-type
.. role:: ansible-option-elements
.. role:: ansible-option-required
.. role:: ansible-option-versionadded
.. role:: ansible-option-aliases
.. role:: ansible-option-choices
.. role:: ansible-option-choices-default-mark
.. role:: ansible-option-default-bold
.. role:: ansible-option-configuration
.. role:: ansible-option-returned-bold
.. role:: ansible-option-sample-bold

.. Anchors

.. _ansible_collections.netscaler.adc.lbparameter_module:

.. Anchors: short name for ansible.builtin

.. Anchors: aliases



.. Title

netscaler.adc.lbparameter module -- Configuration for LB parameter resource.
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. Collection note

.. note::
    This module is part of the `netscaler.adc collection <https://galaxy.ansible.com/netscaler/adc>`_ (version 2.0.0-alpha).

    To install it, use: :code:`ansible-galaxy collection install netscaler.adc`.

    To use it in a playbook, specify: :code:`netscaler.adc.lbparameter`.

.. version_added

.. rst-class:: ansible-version-added

New in netscaler.adc 2.0.0

.. contents::
   :local:
   :depth: 1

.. Deprecated


Synopsis
--------

.. Description

- Configuration for LB parameter resource.


.. Aliases


.. Requirements






.. Options

Parameters
----------

.. rst-class:: ansible-option-table

.. list-table::
  :width: 100%
  :widths: auto
  :header-rows: 1

  * - Parameter
    - Comments

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-allowboundsvcremoval"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-allowboundsvcremoval:

      .. rst-class:: ansible-option-title

      **allowboundsvcremoval**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-allowboundsvcremoval" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      This is used, to enable/disable the option of svc/svcgroup removal, if it is bound to one or more vserver. If it is enabled, the svc/svcgroup can be removed, even if it bound to vservers. If disabled, an error will be thrown, when the user tries to remove a svc/svcgroup without unbinding from its vservers.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry-default:`"ENABLED"` :ansible-option-choices-default-mark:`← (default)`
      - :ansible-option-choices-entry:`"DISABLED"`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-api_path"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-api_path:

      .. rst-class:: ansible-option-title

      **api_path**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-api_path" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Base NITRO API path.

      Define only in case of an ADM service proxy call


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-bearer_token"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-bearer_token:

      .. rst-class:: ansible-option-title

      **bearer_token**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-bearer_token" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Authentication bearer token.

      Needed when doing an ADM service proxy call.


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-computedadccookieattribute"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-computedadccookieattribute:

      .. rst-class:: ansible-option-title

      **computedadccookieattribute**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-computedadccookieattribute" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      ComputedADCCookieAttribute accepts ns variable as input in form of string starting with $ (to understand how to configure ns variable, please check man add ns variable). policies can be configured to modify this variable for every transaction and the final value of the variable after policy evaluation will be appended as attribute to Citrix ADC cookie (for example: LB cookie persistence , GSLB sitepersistence, CS cookie persistence, LB group cookie persistence). Only one of ComputedADCCookieAttribute, LiteralADCCookieAttribute can be set.

      

      Sample usage -

                   add ns variable lbvar -type TEXT(100) -scope Transaction

                   add ns assignment lbassign -variable $lbvar -set "\\\\";SameSite=Strict\\\\""

                   add rewrite policy lbpol \<valid policy expression\> lbassign

                   bind rewrite global lbpol 100 next -type RES\_OVERRIDE

                   set lb param -ComputedADCCookieAttribute "$lbvar"

                   For incoming client request, if above policy evaluates TRUE, then SameSite=Strict will be appended to ADC generated cookie


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-consolidatedlconn"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-consolidatedlconn:

      .. rst-class:: ansible-option-title

      **consolidatedlconn**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-consolidatedlconn" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      To find the service with the fewest connections, the virtual server uses the consolidated connection statistics from all the packet engines. The NO setting allows consideration of only the number of connections on the packet engine that received the new connection.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry-default:`"True"` :ansible-option-choices-default-mark:`← (default)`
      - :ansible-option-choices-entry:`"False"`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-cookiepassphrase"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-cookiepassphrase:

      .. rst-class:: ansible-option-title

      **cookiepassphrase**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-cookiepassphrase" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Use this parameter to specify the passphrase used to generate secured persistence cookie value. It specifies the passphrase with a maximum of 31 characters.


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-dbsttl"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-dbsttl:

      .. rst-class:: ansible-option-title

      **dbsttl**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-dbsttl" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`integer`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Specify the TTL for DNS record for domain based service. The default value of ttl is 0 which indicates to use the TTL received in DNS response for monitors


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-dropmqttjumbomessage"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-dropmqttjumbomessage:

      .. rst-class:: ansible-option-title

      **dropmqttjumbomessage**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-dropmqttjumbomessage" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      When this option is enabled, MQTT messages of length greater than 64k will be dropped and the client/server connections will be reset.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry-default:`"True"` :ansible-option-choices-default-mark:`← (default)`
      - :ansible-option-choices-entry:`"False"`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-httponlycookieflag"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-httponlycookieflag:

      .. rst-class:: ansible-option-title

      **httponlycookieflag**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-httponlycookieflag" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Include the HttpOnly attribute in persistence cookies. The HttpOnly attribute limits the scope of a cookie to HTTP requests and helps mitigate the risk of cross-site scripting attacks.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry-default:`"ENABLED"` :ansible-option-choices-default-mark:`← (default)`
      - :ansible-option-choices-entry:`"DISABLED"`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-instance_id"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-instance_id:

      .. rst-class:: ansible-option-title

      **instance_id**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-instance_id" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      The id of the target NetScaler ADC instance when issuing a Nitro request through a NetScaler ADM proxy.


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-instance_ip"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-instance_ip:

      .. rst-class:: ansible-option-title

      **instance_ip**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-instance_ip" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      :ansible-option-versionadded:`added in netscaler.adc 2.6.0`


      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      The target NetScaler ADC instance ip address to which all underlying NITRO API calls will be proxied to.

      It is meaningful only when having set \ :literal:`mas\_proxy\_call`\  to \ :literal:`true`\ 


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-instance_name"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-instance_name:

      .. rst-class:: ansible-option-title

      **instance_name**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-instance_name" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      The name of the target NetScaler ADC instance when issuing a Nitro request through a NetScaler ADM proxy.


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-is_cloud"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-is_cloud:

      .. rst-class:: ansible-option-title

      **is_cloud**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-is_cloud" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`boolean`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      When performing a Proxy API call with ADM service set this to \ :literal:`true`\ 


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry-default:`false` :ansible-option-choices-default-mark:`← (default)`
      - :ansible-option-choices-entry:`true`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-lbhashalgorithm"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-lbhashalgorithm:

      .. rst-class:: ansible-option-title

      **lbhashalgorithm**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-lbhashalgorithm" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      This option dictates the hashing algorithm used for hash based LB methods (URLHASH, DOMAINHASH, SOURCEIPHASH, DESTINATIONIPHASH, SRCIPDESTIPHASH, SRCIPSRCPORTHASH, TOKEN, USER\_TOKEN, CALLIDHASH).


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry-default:`"DEFAULT"` :ansible-option-choices-default-mark:`← (default)`
      - :ansible-option-choices-entry:`"PRAC"`
      - :ansible-option-choices-entry:`"JARH"`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-lbhashfingers"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-lbhashfingers:

      .. rst-class:: ansible-option-title

      **lbhashfingers**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-lbhashfingers" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`integer`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      This option is used to specify the number of fingers to be used in PRAC and JARH algorithms for hash based LB methods. Increasing the number of fingers might give better distribution of traffic at the expense of additional memory


      .. rst-class:: ansible-option-line

      :ansible-option-default-bold:`Default:` :ansible-option-default:`256`

      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-literaladccookieattribute"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-literaladccookieattribute:

      .. rst-class:: ansible-option-title

      **literaladccookieattribute**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-literaladccookieattribute" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      String configured as LiteralADCCookieAttribute will be appended as attribute for Citrix ADC cookie (for example: LB cookie persistence , GSLB site persistence, CS cookie persistence, LB group cookie persistence).

      

      Sample usage -

                   set lb parameter -LiteralADCCookieAttribute ";SameSite=None"


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-mas_proxy_call"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-mas_proxy_call:

      .. rst-class:: ansible-option-title

      **mas_proxy_call**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-mas_proxy_call" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`boolean`

      :ansible-option-versionadded:`added in netscaler.adc 2.6.0`


      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      If \ :literal:`true`\  the underlying NITRO API calls made by the module will be proxied through a NetScaler ADM node to the target NetScaler ADC instance.

      When \ :literal:`true`\  you must also define the following options: \ :emphasis:`nitro\_auth\_token`\ 

      When \ :literal:`true`\  and adm service is the api proxy the following option must also be defined: \ :emphasis:`bearer\_token`\ 

      When \ :literal:`true`\  you must define a target ADC by defining any of the following parameters

      \ :emphasis:`instance\_ip`\ 

      \ :emphasis:`instance\_id`\ 

      \ :emphasis:`instance\_name`\ 


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry-default:`false` :ansible-option-choices-default-mark:`← (default)`
      - :ansible-option-choices-entry:`true`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-maxpipelinenat"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-maxpipelinenat:

      .. rst-class:: ansible-option-title

      **maxpipelinenat**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-maxpipelinenat" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`integer`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Maximum number of concurrent requests to allow on a single client connection, which is identified by the \<clientip:port\>-\<vserver ip:port\> tuple. This parameter is applicable to ANY service type and all UDP service types (except DNS) and only when "svrTimeout" is set to zero. A value of 0 (zero) applies no limit to the number of concurrent requests allowed on a single client connection


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-monitorconnectionclose"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-monitorconnectionclose:

      .. rst-class:: ansible-option-title

      **monitorconnectionclose**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-monitorconnectionclose" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Close monitoring connections by sending the service a connection termination message with the specified bit set.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry:`"RESET"`
      - :ansible-option-choices-entry-default:`"FIN"` :ansible-option-choices-default-mark:`← (default)`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-monitorskipmaxclient"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-monitorskipmaxclient:

      .. rst-class:: ansible-option-title

      **monitorskipmaxclient**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-monitorskipmaxclient" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      When a monitor initiates a connection to a service, do not check to determine whether the number of connections to the service has reached the limit specified by the service's Max Clients setting. Enables monitoring to continue even if the service has reached its connection limit.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry:`"ENABLED"`
      - :ansible-option-choices-entry-default:`"DISABLED"` :ansible-option-choices-default-mark:`← (default)`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-nitro_auth_token"></div>
        <div class="ansibleOptionAnchor" id="parameter-mas_auth_token"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-mas_auth_token:
      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-nitro_auth_token:

      .. rst-class:: ansible-option-title

      **nitro_auth_token**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-nitro_auth_token" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-aliases:`aliases: mas_auth_token`

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      :ansible-option-versionadded:`added in netscaler.adc 2.6.0`


      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      The authentication token provided by a login operation.


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-nitro_pass"></div>
        <div class="ansibleOptionAnchor" id="parameter-mas_pass"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-mas_pass:
      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-nitro_pass:

      .. rst-class:: ansible-option-title

      **nitro_pass**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-nitro_pass" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-aliases:`aliases: mas_pass`

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      The password with which to authenticate to the NetScaler ADC node.


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-nitro_protocol"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-nitro_protocol:

      .. rst-class:: ansible-option-title

      **nitro_protocol**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-nitro_protocol" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Which protocol to use when accessing the nitro API objects.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry:`"http"`
      - :ansible-option-choices-entry-default:`"https"` :ansible-option-choices-default-mark:`← (default)`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-nitro_timeout"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-nitro_timeout:

      .. rst-class:: ansible-option-title

      **nitro_timeout**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-nitro_timeout" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`float`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Time in seconds until a timeout error is thrown when establishing a new session with NetScaler ADC


      .. rst-class:: ansible-option-line

      :ansible-option-default-bold:`Default:` :ansible-option-default:`310.0`

      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-nitro_user"></div>
        <div class="ansibleOptionAnchor" id="parameter-mas_user"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-mas_user:
      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-nitro_user:

      .. rst-class:: ansible-option-title

      **nitro_user**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-nitro_user" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-aliases:`aliases: mas_user`

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      The username with which to authenticate to the NetScaler ADC node.


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-nsip"></div>
        <div class="ansibleOptionAnchor" id="parameter-mas_ip"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-mas_ip:
      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-nsip:

      .. rst-class:: ansible-option-title

      **nsip**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-nsip" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-aliases:`aliases: mas_ip`

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string` / :ansible-option-required:`required`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      The ip address of the NetScaler ADC appliance where the nitro API calls will be made.

      The port can be specified with the colon (:). E.g. 192.168.1.1:555.


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-preferdirectroute"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-preferdirectroute:

      .. rst-class:: ansible-option-title

      **preferdirectroute**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-preferdirectroute" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Perform route lookup for traffic received by the Citrix ADC, and forward the traffic according to configured routes. Do not set this parameter if you want a wildcard virtual server to direct packets received by the appliance to an intermediary device, such as a firewall, even if their destination is directly connected to the appliance. Route lookup is performed after the packets have been processed and returned by the intermediary device.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry-default:`"True"` :ansible-option-choices-default-mark:`← (default)`
      - :ansible-option-choices-entry:`"False"`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-retainservicestate"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-retainservicestate:

      .. rst-class:: ansible-option-title

      **retainservicestate**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-retainservicestate" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      This option is used to retain the original state of service or servicegroup member when an enable server command is issued.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry:`"True"`
      - :ansible-option-choices-entry:`"False"`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-save_config"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-save_config:

      .. rst-class:: ansible-option-title

      **save_config**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-save_config" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`boolean`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      If \ :literal:`true`\  the module will save the configuration on the NetScaler ADC node if it makes any changes.

      The module will not save the configuration on the NetScaler ADC node if it made no changes.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry-default:`false` :ansible-option-choices-default-mark:`← (default)`
      - :ansible-option-choices-entry:`true`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-startuprrfactor"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-startuprrfactor:

      .. rst-class:: ansible-option-title

      **startuprrfactor**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-startuprrfactor" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`integer`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Number of requests, per service, for which to apply the round robin load balancing method before switching to the configured load balancing method, thus allowing services to ramp up gradually to full load. Until the specified number of requests is distributed, the Citrix ADC is said to be implementing the slow start mode (or startup round robin). Implemented for a virtual server when one of the following is true:

      \* The virtual server is newly created.

      \* One or more services are newly bound to the virtual server. 

      \* One or more services bound to the virtual server are enabled.

      \* The load balancing method is changed.

      This parameter applies to all the load balancing virtual servers configured on the Citrix ADC, except for those virtual servers for which the virtual server-level slow start parameters (New Service Startup Request Rate and Increment Interval) are configured. If the global slow start parameter and the slow start parameters for a given virtual server are not set, the appliance implements a default slow start for the virtual server, as follows:

      \* For a newly configured virtual server, the appliance implements slow start for the first 100 requests received by the virtual server.

      \* For an existing virtual server, if one or more services are newly bound or newly enabled, or if the load balancing method is changed, the appliance dynamically computes the number of requests for which to implement startup round robin. It obtains this number by multiplying the request rate by the number of bound services (it includes services that are marked as DOWN). For example, if the current request rate is 20 requests/s and ten services are bound to the virtual server, the appliance performs startup round robin for 200 requests.

      Not applicable to a virtual server for which a hash based load balancing method is configured.


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-state"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-state:

      .. rst-class:: ansible-option-title

      **state**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-state" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      The state of the resource being configured by the module on the NetScaler ADC node.

      \ :literal:`enabled`\  and \ :literal:`disabled`\  are only valid for resources that can be enabled or disabled.

      When \ :literal:`present`\  the resource will be created if needed and configured according to the module's parameters.

      When \ :literal:`absent`\  the resource will be deleted from the NetScaler ADC node.

      When \ :literal:`enabled`\  the resource will be enabled on the NetScaler ADC node.

      When \ :literal:`disabled`\  the resource will be disabled on the NetScaler ADC node.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry-default:`"present"` :ansible-option-choices-default-mark:`← (default)`
      - :ansible-option-choices-entry:`"absent"`
      - :ansible-option-choices-entry:`"enabled"`
      - :ansible-option-choices-entry:`"disabled"`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-storemqttclientidandusername"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-storemqttclientidandusername:

      .. rst-class:: ansible-option-title

      **storemqttclientidandusername**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-storemqttclientidandusername" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      This option allows to store the MQTT clientid and username in transactional logs


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry:`"True"`
      - :ansible-option-choices-entry:`"False"`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-undefaction"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-undefaction:

      .. rst-class:: ansible-option-title

      **undefaction**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-undefaction" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Action to perform when policy evaluation creates an UNDEF condition. Available settings function as follows:

      \* NOLBACTION - Does not consider LB action in making LB decision.

      \* RESET - Reset the request and notify the user, so that the user can resend the request.

      \* DROP - Drop the request without sending a response to the user.


      .. rst-class:: ansible-option-line

      :ansible-option-default-bold:`Default:` :ansible-option-default:`"\\"NOLBACTION\\""`

      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-useencryptedpersistencecookie"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-useencryptedpersistencecookie:

      .. rst-class:: ansible-option-title

      **useencryptedpersistencecookie**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-useencryptedpersistencecookie" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Encode persistence cookie values using SHA2 hash.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry:`"ENABLED"`
      - :ansible-option-choices-entry-default:`"DISABLED"` :ansible-option-choices-default-mark:`← (default)`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-useportforhashlb"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-useportforhashlb:

      .. rst-class:: ansible-option-title

      **useportforhashlb**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-useportforhashlb" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Include the port number of the service when creating a hash for hash based load balancing methods. With the NO setting, only the IP address of the service is considered when creating a hash.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry-default:`"True"` :ansible-option-choices-default-mark:`← (default)`
      - :ansible-option-choices-entry:`"False"`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-usesecuredpersistencecookie"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-usesecuredpersistencecookie:

      .. rst-class:: ansible-option-title

      **usesecuredpersistencecookie**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-usesecuredpersistencecookie" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Encode persistence cookie values using SHA2 hash.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry:`"ENABLED"`
      - :ansible-option-choices-entry-default:`"DISABLED"` :ansible-option-choices-default-mark:`← (default)`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-validate_certs"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-validate_certs:

      .. rst-class:: ansible-option-title

      **validate_certs**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-validate_certs" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`boolean`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      If \ :literal:`false`\ , SSL certificates will not be validated. This should only be used on personally controlled sites using self-signed certificates.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry-default:`false` :ansible-option-choices-default-mark:`← (default)`
      - :ansible-option-choices-entry:`true`


      .. raw:: html

        </div>

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="parameter-vserverspecificmac"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__parameter-vserverspecificmac:

      .. rst-class:: ansible-option-title

      **vserverspecificmac**

      .. raw:: html

        <a class="ansibleOptionLink" href="#parameter-vserverspecificmac" title="Permalink to this option"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Allow a MAC-mode virtual server to accept traffic returned by an intermediary device, such as a firewall, to which the traffic was previously forwarded by another MAC-mode virtual server. The second virtual server can then distribute that traffic across the destination server farm. Also useful when load balancing Branch Repeater appliances.

      Note: The second virtual server can also send the traffic to another set of intermediary devices, such as another set of firewalls. If necessary, you can configure multiple MAC-mode virtual servers to pass traffic successively through multiple sets of intermediary devices.


      .. rst-class:: ansible-option-line

      :ansible-option-choices:`Choices:`

      - :ansible-option-choices-entry:`"ENABLED"`
      - :ansible-option-choices-entry-default:`"DISABLED"` :ansible-option-choices-default-mark:`← (default)`


      .. raw:: html

        </div>


.. Attributes


.. Notes

Notes
-----

.. note::
   - For more information on using Ansible to manage NetScaler ADC Network devices see \ https://www.ansible.com/integrations/networks/citrixadc\ .

.. Seealso


.. Examples

Examples
--------

.. code-block:: yaml+jinja

    




.. Facts


.. Return values

Return Values
-------------
Common return values are documented :ref:`here <common_return_values>`, the following are the fields unique to this module:

.. rst-class:: ansible-option-table

.. list-table::
  :width: 100%
  :widths: auto
  :header-rows: 1

  * - Key
    - Description

  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="return-changed"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__return-changed:

      .. rst-class:: ansible-option-title

      **changed**

      .. raw:: html

        <a class="ansibleOptionLink" href="#return-changed" title="Permalink to this return value"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`boolean`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Indicates if any change is made by the module


      .. rst-class:: ansible-option-line

      :ansible-option-returned-bold:`Returned:` always

      .. rst-class:: ansible-option-line
      .. rst-class:: ansible-option-sample

      :ansible-option-sample-bold:`Sample:` :ansible-rv-sample-value:`true`


      .. raw:: html

        </div>


  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="return-diff"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__return-diff:

      .. rst-class:: ansible-option-title

      **diff**

      .. raw:: html

        <a class="ansibleOptionLink" href="#return-diff" title="Permalink to this return value"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`dictionary`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Dictionary of before and after changes


      .. rst-class:: ansible-option-line

      :ansible-option-returned-bold:`Returned:` always

      .. rst-class:: ansible-option-line
      .. rst-class:: ansible-option-sample

      :ansible-option-sample-bold:`Sample:` :ansible-rv-sample-value:`{"after": {"key2": "pqr"}, "before": {"key1": "xyz"}, "prepared": "changes done"}`


      .. raw:: html

        </div>


  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="return-diff_list"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__return-diff_list:

      .. rst-class:: ansible-option-title

      **diff_list**

      .. raw:: html

        <a class="ansibleOptionLink" href="#return-diff_list" title="Permalink to this return value"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`list` / :ansible-option-elements:`elements=string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      List of differences between the actual configured object and the configuration specified in the module


      .. rst-class:: ansible-option-line

      :ansible-option-returned-bold:`Returned:` when changed

      .. rst-class:: ansible-option-line
      .. rst-class:: ansible-option-sample

      :ansible-option-sample-bold:`Sample:` :ansible-rv-sample-value:`["Attribute \`key1\` differs. Desired: (\<class 'str'\>) XYZ. Existing: (\<class 'str'\>) PQR"]`


      .. raw:: html

        </div>


  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="return-failed"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__return-failed:

      .. rst-class:: ansible-option-title

      **failed**

      .. raw:: html

        <a class="ansibleOptionLink" href="#return-failed" title="Permalink to this return value"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`boolean`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      Indicates if the module failed or not


      .. rst-class:: ansible-option-line

      :ansible-option-returned-bold:`Returned:` always

      .. rst-class:: ansible-option-line
      .. rst-class:: ansible-option-sample

      :ansible-option-sample-bold:`Sample:` :ansible-rv-sample-value:`false`


      .. raw:: html

        </div>


  * - .. raw:: html

        <div class="ansible-option-cell">
        <div class="ansibleOptionAnchor" id="return-loglines"></div>

      .. _ansible_collections.netscaler.adc.lbparameter_module__return-loglines:

      .. rst-class:: ansible-option-title

      **loglines**

      .. raw:: html

        <a class="ansibleOptionLink" href="#return-loglines" title="Permalink to this return value"></a>

      .. rst-class:: ansible-option-type-line

      :ansible-option-type:`list` / :ansible-option-elements:`elements=string`

      .. raw:: html

        </div>

    - .. raw:: html

        <div class="ansible-option-cell">

      list of logged messages by the module


      .. rst-class:: ansible-option-line

      :ansible-option-returned-bold:`Returned:` always

      .. rst-class:: ansible-option-line
      .. rst-class:: ansible-option-sample

      :ansible-option-sample-bold:`Sample:` :ansible-rv-sample-value:`["message 1", "message 2"]`


      .. raw:: html

        </div>



..  Status (Presently only deprecated)


.. Authors

Authors
~~~~~~~

- Sumanth Lingappa (@sumanth-lingappa)



.. Extra links

Collection links
~~~~~~~~~~~~~~~~

.. raw:: html

  <p class="ansible-links">
    <a href="http://example.com/issue/tracker" aria-role="button" target="_blank" rel="noopener external">Issue Tracker</a>
    <a href="http://example.com" aria-role="button" target="_blank" rel="noopener external">Homepage</a>
    <a href="http://example.com/repository" aria-role="button" target="_blank" rel="noopener external">Repository (Sources)</a>
  </p>

.. Parsing errors

