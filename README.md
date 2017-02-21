EWP Abstract Contact Type
=========================

* [What is the status of this document?][statuses]
* [See the index of all other EWP Specifications][develhub]


Summary
-------

This repository contains XML Schema used in some EWP APIs in contexts when
multiple, non-identifiable, abstract contact entities need to be attached to a
business entity. It follows the same [versioning rules][compat-rules] as all
EWP APIs do.


About this data type
--------------------

In our research, we found that contact information provided in fact sheets, and
in other places, can sometimes by much more generic that one might think. In
particular, it may refer not only to specific people, but also - for example -
to offices.

To reflect this, we have created this generic type. A contact of this type can
be attached to any other entity. It can be displayed to the end user, but it is
not necessarily intended to be stored in the client's database in a structured
format (it can be cached though).

This type builds upon two other EWP data types:

* [Phone Number data type]
  (https://github.com/erasmus-without-paper/ewp-specs-types-phonenumber)
* [Address data type]
  (https://github.com/erasmus-without-paper/ewp-specs-types-address)


The Schema
----------

See attached [`schema.xsd`](schema.xsd) file.


Examples
--------

```xml
<contact>
    <!-- A minimal example. -->
    <contact-name>IRO Office</contact-name>
    <email>iro@uio.no</email>
</contact>
```

```xml
<contact
    xmlns="https://github.com/erasmus-without-paper/ewp-specs-types-contact/tree/master"
    xmlns:a="https://github.com/erasmus-without-paper/ewp-specs-types-address/tree/master"
    xmlns:p="https://github.com/erasmus-without-paper/ewp-specs-types-phonenumber/tree/stable-v1"
>
    <!-- Servers may provide names in multiple languages and alphabets. -->
    <contact-name xml:lang="en">Ivan Sidorov (visas and insurance)</contact-name>
    <contact-name xml:lang="ru-Latn">Ivan Petrovich Sidorov (vizy i strakhovaniye)</contact-name>
    <contact-name xml:lang="ru-Cyrl">Иван Петрович Сидоров (визы и страхование)</contact-name>

    <!-- This particular contact describes a person. -->
    <person-given-names xml:lang="ru-Latn">Ivan Petrovich</person-given-names>
    <person-given-names xml:lang="ru-Cyrl">Иван Петрович</person-given-names>
    <person-family-name xml:lang="ru-Latn">Sidorov</person-family-name>
    <person-family-name xml:lang="ru-Cyrl">Сидоров</person-family-name>

    <p:phone-number>
        <p:e164>+4723456789</p:e164>
    </p:phone-number>
    <p:phone-number>
        <p:e164>+4722222222</p:e164>
        <p:ext>3407</p:ext>
    </p:phone-number>
    <p:fax-number>
        <p:other-format>(23) 456789</p:other-format> <!-- discouraged -->
    </p:fax-number>
    <email>ivan@uio.no</email>
    <a:street-address> <!-- ... --> </a:street-address>
    <a:mailing-address> <!-- ... --> </a:mailing-address>
    <role-description xml:lang="en">
        Ivan Sidorov is advising incoming students in regard to visas and insurance.

        (This field may also contain other information, which is not present in the
        format itself, e.g. calling hours.)
    </role-description>
</contact>
```


[develhub]: http://developers.erasmuswithoutpaper.eu/
[statuses]: https://github.com/erasmus-without-paper/ewp-specs-management#statuses
[compat-rules]: https://github.com/erasmus-without-paper/ewp-specs-architecture/#backward-compatibility-rules
