ACK Thinning
============
aka, ack scaling, ack reduction, ack optimization

ACK thinning is about reducing the ACK traffic without impacting the
application performance.

ACKs are used in any ARQ_ based transport over unreliable links for the
receiver to signal the sender of all the packets that it received or inversely
the packets it missed.

Transports such as TCP_, QUIC_, SCTP_, DCCP_ all employ ARQ_ and thus some form
of ACKing.

Apart from signaling the loss of packets, ACKs also help the sender to estimate
RTT and clocking the packets to be sent.

Why ACK Thinning?
-----------------
* On cloud servers: Improves performance because less number of packets to be
  handled. Cloud server performance is mostly calculated on per-packet basis
  and ACKs form a significant proportion.
* Wireless networks: Reduces contention. ACKs share the same medium as data
  traffic and thus induce contention. The inter-frame spacing required as a
  guard in wireless settings is same for any packet regardless of its size
  i.e., even though ACK packet size is small it still has significant impact on
  contention.
* In Assymetric links such as LTE, the ACK traffic could hinder overall
  performance [QUOTE-Gory's paper]

Side-effects of ACK Thinning
----------------------------
RTT calculation
Send Bursts and impact on buffering

Experiments with TCP ACK thinning
---------------------------------
Changes done to TCP to experiment with ACK Thinning?
Impact on RTT calculation on normal links?
Impact on RTT calculation on lossy (10% loss) links?
Impact on RTT calculation on high-jitter (4ms-80ms) links?
    - Also check impact on buffering
    - Impact on send rate

DOCSIS and ACK Thinning
-----------------------

Wi-Fi aggregation and its impact on ACKs
----------------------------------------

DCCP and ACK
------------

ACK thinning in context to Wi-Fi networks
-----------------------------------------

.. _ARG: https://en.wikipedia.org/wiki/Automatic_repeat_request
.. _TCP: https://tools.ietf.org/html/rfc793
.. _SCTP: https://tools.ietf.org/html/rfc4960
.. _DCCP: https://tools.ietf.org/html/rfc4340

