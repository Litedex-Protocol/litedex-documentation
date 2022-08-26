# Security Preventive

#### Definition of Centralization Risks

Centralization risks are vulnerabilities that can be exploited both by malicious developers of a project as well as malicious outside attackers. They can be taken advantage of in rug pulls, infinite minting exploits, and many other types of attacks.\
\
**Litedex implement two securities to mitigate the problem.**\
****\
****_Network : BSC Mainnet_

{% tabs %}
{% tab title="Multi-signature wallets" %}
_**`Litedex Assign the privileged roles to multi-signature wallets (3 of 5 signers).`**_



_**Multi-signature proxy address :** 0x76111cC93b32F9B83C45E0d3155995C6f40916aE_

_**Internal multi-signature address.**_

* _**Signer 1 :** 0x3b63E928047A7Ec4fA54f226503522964d690a95_&#x20;
* _**Signer 2 :** 0x1651ceCaA1870a595282680F0f773ad34B142Fd0_
* _**Signer 3 :** 0x067e2EdABEF143773A5748e5483EbEB0247961e1_
* _**Signer 4 :** 0xCE0e6F69eB6D0BFe6149d8e6FaD87961Be31C4B2_
* _**Signer 5 :** 0xF822eA79E74634F4bcad0D41E7f58bE3242c85C7_
{% endtab %}

{% tab title="Timelock 6-hours" %}
_**`Litedex implement Time-lock with 6 hours latency, for awareness of privileged operations.`**_\
_**``**_\
_**``Timelock Address :**_ 0xA06b1A094A3d84f4D67d6210dD3e121870faaDAF\
_**Proposer Address :** 0x76111cC93b32F9B83C45E0d3155995C6f40916aE_\
_**Admin Address :** 0x76111cC93b32F9B83C45E0d3155995C6f40916aE_\
_**Executor Address :** 0x76111cC93b32F9B83C45E0d3155995C6f40916aE_
{% endtab %}
{% endtabs %}
