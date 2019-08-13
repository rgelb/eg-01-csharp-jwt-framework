# Example 1: C# .NET Framework Service Integration

Repository: [eg-01-csharp-jwt-framework](https://github.com/docusign/eg-01-csharp-jwt-framework)

<!--
## Articles and Screencasts

* Guide: Using OAuth JWT flow with DocuSign.
* Screencast: Using OAuth JWT flow with DocuSign.
* Guide: Sending an envelope with the Node.JS SDK.
* Screencast: Sending an example with Node.JS SDK.
-->

## Introduction

This software is an example of a **System Integration**.
This type of application interacts with DocuSign on its
own. There is no user interface and no user is present
during normal operation.

The application uses the OAuth JWT grant flow to impersonate
a user in the account.

This launcher example includes two examples:
1. Send an html, Word, and PDF file in an envelope to be signed.
1. List the envelopes in the account that are less than 30 days old.

## Installation

Requirements: C# and .NET Framework v4.5 or later.

This repository has been tested as a Visual Studio 2017
Community Edition solution.

### Short installation instructions
* Download or clone this repository.
* The repository includes a Visual Studio 2017 solution file and 
  NuGet package references in the project file.
* Configure the project by editing the existing project file
  `common/App.config`
  
  See the Configuration section, below, for more information.
* The solution's Main class is in `common/Program.cs`

## Configure the example

Configure the example via the `common/App.config` file.

**Recommendation:** add `common/App.config` to your `.gitignore` file so your 
private information will not be added to your repository.

Do not store your Integration Key, private key, or other
private information in your code repository.

### Creating the Integration Key
Your DocuSign Integration Key must be configured for a JWT OAuth authentication flow:
* Using the DocuSign Admin tool,
  create a public/private key pair for the integration key.
  Store the private key
  in a secure location. You can use a file or a key vault.
* The example requires the private key. Store the private key in the
  `App.config` file.
* If you will be using individual consent grants, you must create a
  `Redirect URI` for the key. Any URL can be used. By default, this
  example uses `https://www.docusign.com`

### The impersonated user's guid
The JWT will impersonate a user within your account. The user can be
an individual or a user representing a group such as "HR".

The example needs the guid assigned to the user.

The guid value for each user in your account is available from
the DocuSign Admin tool in the **Users** section.
To see a user's guid, **Edit** the user's information.
On the **Edit User** screen, the guid for the user is shown as
the `API Username`.

## Run the examples

Build, then run the solution to see its output.

## The common files
This repository is configured for use with .NET Framework.
The source files, stored in the `/common` directory,
also work (unchanged) with .NET Core.

A [.NET Core version](https://github.com/docusign/eg-01-csharp-jwt-core)
of this example is also available. 
It uses the same common set of source files,
but is configured as a .NET Core solution for
Visual Studio 2017.

## Support, Contributions, License

Submit support questions to [StackOverflow](https://stackoverflow.com). Use tag `docusignapi`.

Contributions via Pull Requests are appreciated. Pull requests for the common
files must be contributed to the 
[eg-01-csharp-jwt-common](https://github.com/docusign/eg-01-csharp-jwt-common)
repository.
See the [Contributing.md](https://github.com/docusign/eg-01-csharp-jwt-common/blob/master/docs/Contributing.md/)
file for information on contributing to this project.

All contributions must use the MIT License.

This repository uses the MIT license, see the
LICENSE file.
