# Score - Genomic File Transfer & Object Storage

[<img hspace="5" src="https://img.shields.io/badge/chat-on--slack-blue?style=for-the-badge">](http://slack.overture.bio)
[<img hspace="5" src="https://img.shields.io/badge/License-gpl--v3.0-blue?style=for-the-badge">](https://github.com/overture-stack/score/blob/develop/LICENSE)
[<img hspace="5" src="https://img.shields.io/badge/Code%20of%20Conduct-2.1-blue?style=for-the-badge">](code_of_conduct.md)

<div>
<img align="right" width="85vw" src="icon-score.png" alt="ego-logo" hspace="30"/>
</div>

Advances in next-generation sequencing have drastically increased the velocity and volume of genomic data. This has outpaced on-premise computing and storage capacities propelling researchers to the cloud. Score is a data transfer service that handles genomic data payloads across geographically distributed cloud storage solutions.

Score commonly works in tandem with our metadata service, [Song](https://github.com/overture-stack/SONG). As Score facilitates object storage in the cloud, Song runs in parallel to validate, assign identifiers, track, and manage the publication and access of genomic and associated metadata. 

<!--Blockqoute-->

</br>

> 
> <div>
> <img align="left" src="ov-logo.png" height="90"/>
> </div>
> 
> *Score is a vital service within the [Overture](https://www.overture.bio/) research software ecosystem. With our genomics data management solutions, scientists can significantly improve the lifecycle of their data and the quality of their research. See our [related products](#related-products) for more information on what Overture can offer.*
> 
> 

<!--Blockqoute-->

## Technical Specifications

- Written in JAVA 
- Supports AWS S3, Azure, Google Cloud, Openstack with Ceph, Minio and all other S3-compliant cloud storage solutions
- Built-in [Samtools](http://www.htslib.org/) functionality including BAM and CRAM file slicing by genomic region 
- ACL security using [OAuth 2.0](https://oauth.net/2/) and scopes based on study codes
- Multipart Uploads and Downloads
- REST API with [Swagger UI](https://swagger.io/tools/swagger-ui/)
- [MD5sum](https://www.intel.com/content/www/us/en/support/programmable/articles/000078103.html) validation


## Documentation

- See our Developer [wiki](https://github.com/overture-stack/score/wiki)
- For our user installation guide see our website [here](https://www.overture.bio/documentation/score/installation/installation/)
- For user guidance see our website [here](https://www.overture.bio/documentation/score/user-guide/admin-ui/)

## Support & Contributions

- Filing an [issue](https://github.com/overture-stack/score/issues)
- Making a [contribution](CONTRIBUTING.md)
- Connect with us on [Slack](http://slack.overture.bio)
- Add or Upvote a [feature request](https://github.com/overture-stack/score/issues?q=is%3Aopen+is%3Aissue+label%3Anew-feature+sort%3Areactions-%2B1-desc)

## Related Products 

<div>
  <img align="right" alt="Overture overview" src="https://www.overture.bio/static/124ca0fede460933c64fe4e50465b235/a6d66/system-diagram.png" width="45%" hspace="5">
</div>

Overture is an ecosystem of research software tools, each with narrow responsibilities, designed to address the adapting needs of genomics research. 

The Overture **Data Management System** (DMS) is a fully functional and customizable data portal built from a packaged collection of Overtures microservices. For more information on DMS, read our [DMS documentation](https://www.overture.bio/documentation/dms/).

See the links below for additional information on our other research software tools:

</br>

|Product|Description|
|---|---|
|[Ego](https://www.overture.bio/products/ego/)|An authorization and user management service|
|[Ego UI](https://www.overture.bio/products/ego-ui/)|A UI for managing EGO authentication and authorization services|
|[Score](https://www.overture.bio/products/score/)| Transfer data quickly and easily to and from any cloud-based storage system|
|[Song](https://www.overture.bio/products/song/)|Catalog and manage metadata of genomics data spread across cloud storage systems|
|[Maestro](https://www.overture.bio/products/maestro/)|Organizing your distributed data into a centralized Elasticsearch index|
|[Arranger](https://www.overture.bio/products/arranger/)|Organize an intuitive data search interface, complete with customizable components, tables, and search terms|
