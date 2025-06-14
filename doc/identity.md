<div align="center">
	<p>
		<img alt="Thoughtworks Logo" src="https://raw.githubusercontent.com/twplatformlabs/static/master/psk_banner.png" width=500 />
	</p>
  <h3>1.2 Identity and Authorization</h3>
</div>
<br />

![bootstrap](https://img.shields.io/badge/document-EarlyDraft-yellow.svg?style=for-the-badge&logo=markdown)  

Identity and authorization is a _solve-for-first_ issue, with deep repercussions across a platform implementation.    

A general Identity Provider (IDP) is itself a capability that will need to be made available to platform users as well as incorporated into the platform.  

Effective productization of platform capabilities requires the abstraction of the platform user's identity from the underlying infrastructure IAM capabilities. (As you are experiencing right now as you read this document on GitHub. Your identity integration with GitHub is not built around direct or SSO integration with their infrastructure providers IAM capability. Customer identity on GitHub is an Abstraction layer.)  

If you are going to deliver a self-serve experience for internal consumers of an engineering platform, how will you enable those internal teams to self-manage team creation and membership? When a team adds a team member, how will that team member automatically have access to all of the team resources?  

The Platform Starter Kit integrates Github and Github Teams information as AuthN and AuthZ, respectively. This is a frequently used pattern and simpilifies dmeonstrating the resulting experience. It is assumed that internal customers will already have been granted access to the company's GitHub organization and can self-manage team creation and membership. Using a Platform touchpoint (CLI, Developer Portal), internal customers can onboard their github team and automatically inherit this team-level authorization across all Platform resources.  

Lab environments and working code examples make use of **auth0.com** for oauth2 workflows.  

<hr>  

[<kbd> <br> Home <br> </kbd>](../README.md)
