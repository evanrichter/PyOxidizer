.. _apple_codesign:

==================
Apple Code Signing
==================

The ``apple-codesign`` Rust crate and its corresponding ``rcodesign`` CLI
tool implement code signing for Apple platforms.

We believe this crate provides the most comprehensive implementation of Apple
code signing outside the canonical Apple tools. We have support for the following
features:

* Signing Mach-O binaries (the executable file format on Apple operating systems).
* Signing, notarizing, and stapling directory bundles (e.g. ``.app`` directories).
* Signing, notarizing, and stapling XAR archives / ``.pkg`` installers.
* Signing, notarizing, and stapling disk images / ``.dmg`` files.

**What this all means is that you can sign, notarize, and release Apple software
from Linux and Windows without needing access to proprietary Apple software!**

Other features include:

* Built-in support for using smart cards (e.g. YubiKeys) for signing and
  key/certificate management.
* A *remote signing* mode that enables you to delegate just the low-level
  cryptographic signature generation to a remote machine. This allows you to
  do things like have a CI job initiate signing but use a YubiKey on a remote
  machine to create cryptographic signatures. See
  :ref:`apple_codesign_remote_signing` for more.
* Certificate Signing Request (CSR) support to enable arbitrary private keys
  (including those generated on smart card devices) to be easily exchanged for
  Apple-issued code signing certificates.
* Support for dumping and diffing data structures related to code signatures.
* Awareness of Apple's public PKI infrastructure, including CA certificates
  and custom X.509 extensions and OIDs used by Apple.
* Documentation and code that are likely a treasure trove for others wanting
  to play with Apple code signing.

The canonical home of this project is
https://github.com/indygreg/PyOxidizer/tree/main/apple-codesign.
While this project is developed inside a larger monorepository, it is designed
to be used as a standalone project.

.. toctree::
   :maxdepth: 2

   apple_codesign_getting_started
   apple_codesign_rcodesign
   apple_codesign_certificate_management
   apple_codesign_smartcard
   apple_codesign_concepts
   apple_codesign_quirks
   apple_codesign_debugging
   apple_codesign_remote_signing
   apple_codesign_remote_signing_protocol
   apple_codesign_remote_signing_design
   apple_codesign_gatekeeper
   apple_codesign_custom_assessment_policies
