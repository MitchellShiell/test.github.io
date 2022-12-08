<!--Ego ReadMe Draft 2-->

# Ego - Authentication and Authorization Micro-Service

[<img hspace="5" src="https://img.shields.io/docker/pulls/overture/ego?style=for-the-badge">](#developer)
[<img hspace="5" src="https://img.shields.io/badge/chat-on--slack-blue?style=for-the-badge">](http://slack.overture.bio)
[<img hspace="5" src="https://img.shields.io/badge/License-gpl--v3.0-blue?style=for-the-badge">](https://github.com/overture-stack/ego/blob/develop/LICENSE)
[<img hspace="5" src="https://img.shields.io/badge/Code%20of%20Conduct-2.1-blue?style=for-the-badge">](code_of_conduct.md)

<!-- Replace slack with discourse once setup -->

<div>
<img align="right" width="100vw" vspace="5" src="icon-ego.png" alt="ego-logo" hspace="30"/>
</div>

Access to sensitive and valuable information requires complex and secure methods to verify users and authorize what data and applications they are allowed to access. [Ego](https://www.overture.bio/products/ego/) is an open-source authentication and authorization microservice, providing secure user registration and permission management. Ego uses well-known single-sign-on identity providers like Google, GitHub, LinkedIn and ORCiD in place of managing usernames and passwords. If you'd like to run Ego with a user interface see our [Ego UI repo](https://github.com/overture-stack/ego-ui).

## Technical Specifications

- [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](https://auth0.com/docs/authenticate/protocols/openid-connect-protocol) compliant
- Written in JAVA 
- Developed with [Sprint Boot](https://spring.io/projects/spring-boot) and [Spring Security Frameworks](https://spring.io/projects/spring-security)
- Scalable with [JSON Web Tokens (JWT)](https://jwt.io/)
- For more information visit our [wiki](https://www.overture.bio/documentation/ego/)

> </br>
> <div>
> <img align="left" src="ov-logo.png" height="100" hspace="20"/>
> </div>
> 
> Ego is a key service within the [Overture](https://www.overture.bio/) genomics research software ecosystem. Genomic data can be overwhelming to manage, and scientists don’t have the time or resources for automation. With our genomic data management solutions, researchers can significantly improve the lifecycle of their data and the quality of their publications. See our [Related Products](#related-products) for more information on what Overture offers.
>
> </br>

## Documentation

- See our Developer [wiki](https://github.com/overture-stack/ego/wiki)
- For user installation guide see our website [here](https://www.overture.bio/documentation/ego/installation/)
- For administrative guidance see our website [here](https://www.overture.bio/documentation/ego/user-guide/admin-ui/)

## Developer Setup

**1. Set up a google oauth client app. [See here](https://www.overture.bio/documentation/ego/installation/prereq/#google) for more details**

- *Note it may take **5 minutes to a few hours** for settings to take effect*

</br>

**2. Clone or Download the repository and update the  ```docker-compose-all.yml``` file with your client id and secret** 

```
spring.security.oauth2.client.registration.google.clientId : "<insert-provided-client-Id>"
spring.security.oauth2.client.registration.google.clientSecret: "<insert-provided-clientSecret>"
```

**3. Open Docker desktop and then run the following command from your CLI**

```
docker-compose -f docker-compose-all.yml up 
```


**4. Ego requires seed data to authorize the Ego UI as a client using the following command**

*Alternatively if you have ```Make``` installed you can run  ```make init-db```*
```
docker exec ego-postgres-1  psql -h localhost -p 5432 -U postgres -d ego --command "INSERT INTO EGOAPPLICATION (name, clientId, clientSecret, redirectUri, description, status, errorredirecturi) VALUES ('ego ui', 'ego-ui', 'secret', 'http://localhost:8080/', '...', 'APPROVED', 'http://localhost:8080/error') on conflict do nothing"
```

**5. You can now access the Ego UI through ```http://localhost:8080/ego-ui```**
- This will require your google sign in 
- Once signed in you will have access to the admin dashboard
- The Ego swagger ui can be located at ```http://localhost:8080/swagger-ui.html```

## Making a Contribution

- [Making a Contribution](CONTRIBUTING.md)
- [Filing an issue](https://github.com/overture-stack/ego/issues)

## Feedback

- Connect with us on [Slack](http://slack.overture.bio)
- [Upvote](https://github.com/overture-stack/ego/issues?q=is%3Aopen+is%3Aissue+label%3Anew-feature+sort%3Areactions-%2B1-desc) feature requests

## Related Products 

<div>
  </br>
  <img align="right" alt="Overture overview" src="https://www.overture.bio/static/124ca0fede460933c64fe4e50465b235/a6d66/system-diagram.png" width="50a%" vspace="10" hspace="10">

</div>

Ego is a central component in the [Overture Data Management System (DMS)](https://www.overture.bio/documentation/dms/). Overture's modular architecture allows you to utilize and mix any of our products to fulfill your individual needs. Our core technologies can be used as standalone services, and can alsobe deployed in concert as an end-to-end data management system (DMS) designed to satisfy the needs of modern large-scale genomics research. For more information on our DMS, please see our [DMS documentation](https://www.overture.bio/documentation/dms/).

Overtures' modular architecture allows you to utilize and mix any of our products to fulfill your individual needs. Our core technologies, however, can also work in concert as an end-to-end data management system (DMS) designed to satisfy the needs of modern large-scale genomic research. For more information on our DMS, please see our [DMS documentation](https://www.overture.bio/documentation/dms/).

See the links below for additional information on our other modular solutions:

|Product|Description|
|---|---|
|[Ego](https://www.overture.bio/products/ego/)|An authorization and user management service|
|[Ego UI](https://www.overture.bio/products/ego-ui/)|A UI for managing EGO authentication and authorization services|
|[Score](https://www.overture.bio/products/score/)| Transfer data quickly and easily to and from any cloud-based storage system|
|[Song](https://www.overture.bio/products/song/)|Catalog and manage metadata of genomics data spread across cloud storage systems|
|[Maestro](https://www.overture.bio/products/maestro/)|Organizing your distributed data into a centralized Elasticsearch index|
|[Arranger](https://www.overture.bio/products/arranger/)|Organize an intuitive data search interface, complete with customizable components, tables, and search terms|

