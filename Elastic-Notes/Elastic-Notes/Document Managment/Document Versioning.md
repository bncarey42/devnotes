# Document Versioning
NOT A REVISION HISTORY OF DOCUMENTS

ES only stores the most recent version of the document

ES stores a `_version ` metadata field with every document (an integer incremented when modifying a document)

not included in \_search queries by default (but ES can be configed)

### Types of versioning

the defaulted is called internal versiong

External versioning is then versions are maintained outside of ES

E.g. when documents are being fed from a primary store in a RDBMS

constrained to being a natural number

![](Document%20Versioning/image.png)

this is all old because of primary terms and sequence numbers. primary use is doing (legacy) optimistic concurrency contro