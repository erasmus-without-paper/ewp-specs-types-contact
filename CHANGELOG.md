Release notes
=============

This document describes all the changes made to the *EWP Abstract Contact Type*
document, starting from its first beta draft version.


1.1.0
-----

* New element: `<person-gender>`.

* Added a clarification that it is allowed (but NOT RECOMMENDED) for a person
  to have a family name in certain language/alphabet, but also be missing the
  given names in this language/alphabet, etc.

* Added a recommendation for the servers that email addresses should be
  provided, because clients might want to use them to identify the contact
  (e.g. if they choose to import it into their systems).


1.0.0
-----

* Changed XML Namespace. Replaced the draft `master` branch:

  ```
  https://github.com/erasmus-without-paper/ewp-specs-types-contact/tree/master
  ```

  With the `stable-v1` one:

  ```
  https://github.com/erasmus-without-paper/ewp-specs-types-contact/tree/stable-v1
  ```

* Changed XML Namespace of the Phone Number data type (it is now `stable-v1`).

This is the first official stable version, accepted by all the partners
([details here](https://github.com/erasmus-without-paper/general-issues/issues/24)).


0.3.0
-----

* New optional elements: `<person-given-names>` and `<person-family-name>`.

* Specified how servers should provide contact names in multiple languages or
  multiple scripts. Examples were updated to reflect that.


0.2.0
-----

* The `<role-description>` element is now recommended only in specific
  contexts (because in some other contexts the contact's role might be
  declared via other means).

* `Contact` data type can now be used directly (without the `<contact>`
  wrapper).


0.1.0
-----

Initial release.
