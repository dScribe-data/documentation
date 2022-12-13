# SAP Business Warehouse (BW) on HANA or BW4/HANA

## SUMMARY

This document gives an overview of dScribe’s out-of-the-box connector for SAP Business Warehouse (SAP BW).

## AVAILABLE METADATA

Via this file based connector, all SAP BW queries available in a SAP BW client can be automatically cataloged, including information on which InfoProvider these are built.

&#x20;

The following metadata is retrieved per BW Query: (in bold indicated the fields made visible in dScribe). Some of the fields are not used but are made available as per standard output by SAP.

·         MAPNAME: the technical name of the BW query

·         NODE\_KEY: L1 hierarchy

·         RELATKEY: the hierarchical structure used to link objects which eachother

·         OBJECT: Type of SAP BW object (Query, CompositeProvider, DatastoreObject, Filter,          Characteristic restriction, Selection, Variable,..)

·         TEXT: the description of the query

·         VALUE: the technical value of the individual BW object (per line)

·         OBJVERS: brings along whether or not the object is ‘A(ctive)’ and thus usable.

·         COMPID: technical field containing the query name (only on the query available)

·         VERSION: technical field containing the version of the object (not used further in dScribe)

·         COMPDIM: technical field containing the dimension of the object (not used further in dScribe)

·         OBJSTAT: description of the ‘OBJVERS’ object (ACT being Active)

·         CONTREL: not used

·         CONTTIMESTMP: not used

·         OWNER: the person who originally created the BW query

·         BWAPPL: not used

·         ACTIVFL: ‘X’ indicates the object is active

·         TIMESTMP: Timestamp of last change of the BW query

·         TSTPNM: Name of the person that has last changed the object

·         TSTPDAT: Date of the last change

·         TSTPTIM: Time of the last change

·         LASTUSED: Timestamp of the last time the object was used

·         CREATED: Timestamp of creation of the BW query

·         CHANGED\_WITH: not used

·         INFOAREA: SAP BW Infoarea under which the BW query is saved.&#x20;
