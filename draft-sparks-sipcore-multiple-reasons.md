---
title: "Multiple SIP Reason Header Field Values"
abbrev: "Multiple reasons"
docname: draft-sparks-sipcore-multiple-reasons-latest
category: std
updates: 3326

ipr: trust200902
area: ART
workgroup: SIPCORE Working Group
keyword: Internet-Draft

stand_alone: yes
smart_quotes: no
pi: [toc, sortrefs, symrefs]

author:
 -
    name: Robert Sparks
    organization: 
    email: rjsparks@nostrum.com

normative:
  RFC3326: RFC3326
  
informative:


--- abstract

The RFC 3326 definition of the SIP Reason Header Field requires multiple values to one per protocol values. Practice shows there is value in allowing multiple values with the same protocol value. This update to RFC 3326 relaxes the restriction to allow multiple values for an indicated registered protocol when that protocol defines what multiple values in the Reason header field sharing that protocol means.

--- middle

# Introduction

{{RFC 3326}} definition of the SIP Reason Header Field requires multiple values to one per protocol values. Practice shows there is value in allowing multiple values with the same protocol value. This update to RFC 3326 relaxes the restriction to allow multiple values for an indicated registered protocol when that protocol defines what multiple values in the Reason header field sharing that protocol means.

# Conventions and Definitions

{::boilerplate bcp14-tagged}

# Update to RFC3326

OLD:
   A SIP message MAY contain more than one Reason value (i.e., multiple
   Reason lines), but all of them MUST have different protocol values
   (e.g., one SIP and another Q.850).  An implementation is free to
   ignore Reason values that it does not understand.

NEW:

   A SIP message MAY contain more than one Reason value (i.e., multiple
   Reason lines). If the registered protocol for the Reason value specifies
   what it means for multiple values to occur in one message, more than one
   value for that protocol MAY be present. Otherwise, the MUST only one be
   one value per protocol provided (e.g., one SIP and another Q.850).  An
   implementation is free to ignore Reason values that it does not understand.

# Security Considerations

This document adds no security considerations to the use of SIP. The security considerations in {{RFC3326}} and those in any registered protocols used in Reason header field values should be considered.

# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
This text is based on discussions at a STIR working group interim meeting.
