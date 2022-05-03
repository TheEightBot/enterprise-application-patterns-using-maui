![](./media/image1.png)

Book title

Book subtitle

Author Name

![](./media/image2.png)

PUBLISHED BY

DevDiv, .NET and Visual Studio product teams

A division of Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2017 by Microsoft Corporation

All rights reserved. No part of the contents of this book may be
reproduced or transmitted in any form or by any means without the
written permission of the publisher.

This book is provided "as-is" and expresses the author's views and
opinions. The views, opinions and information expressed in this book,
including URL and other Internet website references, may change without
notice.

Some examples depicted herein are provided for illustration only and are
fictitious. No real association or connection is intended or should be
inferred.

Microsoft and the trademarks listed at http://www.microsoft.com on the
"Trademarks" webpage are trademarks of the Microsoft group of companies.
All other marks are property of their respective owners.

**Author:** David Britch

**Developer:** Javier Suarez Ruiz (Plain Concepts)

**Participants and reviewers:** Craig Dunn, Tom Opgenorth

**Editor:** John Meade (Populus Group)

Contents

Preface [iv](#_Toc484430859)

Purpose [iv](#purpose)

What\'s left out of this guide\'s scope
[iv](#whats-left-out-of-this-guides-scope)

Who should use this guide [iv](#who-should-use-this-guide)

How to use this guide [v](#how-to-use-this-guide)

Introduction [1](#_Toc484430864)

Sample application [2](#sample-application)

Sample application architecture [2](#sample-application-architecture)

Mobile app [4](#mobile-app)

**eShopOnContainers.Core project** [5](#eshoponcontainers.core-project)

**Platform projects** [6](#platform-projects)

Summary [6](#summary)

MVVM [7](#_Toc484430871)

The MVVM pattern [7](#the-mvvm-pattern)

View [8](#view)

ViewModel [8](#viewmodel)

Model [9](#model)

Connecting view models to views [9](#connecting-view-models-to-views)

Creating a view model declaratively
[10](#creating-a-view-model-declaratively)

Creating a view model programmatically
[10](#creating-a-view-model-programmatically)

Creating a view defined as a data template
[10](#creating-a-view-defined-as-a-data-template)

Automatically creating a view model with a view model locator
[11](#automatically-creating-a-view-model-with-a-view-model-locator)

Updating views in response to changes in the underlying view model or
model
[12](#updating-views-in-response-to-changes-in-the-underlying-view-model-or-model)

UI interaction using commands and behaviors
[13](#ui-interaction-using-commands-and-behaviors)

Implementing commands [13](#implementing-commands)

Implementing behaviors [15](#implementing-behaviors)

Summary [17](#summary-1)

Dependency injection [18](#_Toc484430886)

Introduction to dependency injection
[18](#introduction-to-dependency-injection)

Registration [20](#registration)

Resolution [21](#resolution)

Managing the lifetime of resolved objects
[22](#managing-the-lifetime-of-resolved-objects)

Summary [23](#summary-2)

Communicating between loosely coupled components [24](#_Toc484430892)

Introduction to MessagingCenter [24](#introduction-to-messagingcenter)

Defining a message [26](#defining-a-message)

Publishing a message [26](#publishing-a-message)

Subscribing to a message [27](#subscribing-to-a-message)

Unsubscribing from a message [27](#unsubscribing-from-a-message)

Summary [27](#summary-3)

Navigation [28](#_Toc484430899)

Navigating between pages [29](#navigating-between-pages)

Creating the NavigationService instance
[29](#creating-the-navigationservice-instance)

Handling navigation requests [30](#handling-navigation-requests)

Navigating when the app is launched
[32](#navigating-when-the-app-is-launched)

Passing parameters during navigation
[33](#passing-parameters-during-navigation)

Invoking navigation using behaviors
[34](#invoking-navigation-using-behaviors)

Confirming or cancelling navigation
[34](#confirming-or-cancelling-navigation)

Summary [34](#summary-4)

Validation [35](#_Toc484430908)

Specifying validation rules [36](#specifying-validation-rules)

Adding validation rules to a property
[37](#adding-validation-rules-to-a-property)

Triggering validation [38](#triggering-validation)

Triggering validation manually [38](#triggering-validation-manually)

Triggering validation when properties change
[39](#triggering-validation-when-properties-change)

Displaying validation errors [39](#displaying-validation-errors)

Highlighting a control that contains invalid data
[40](#highlighting-a-control-that-contains-invalid-data)

Displaying error messages [43](#displaying-error-messages)

Summary [44](#summary-5)

Configuration management [45](#_Toc484430918)

Creating a settings class [45](#creating-a-settings-class)

Adding a setting [46](#adding-a-setting)

Data binding to user settings [47](#data-binding-to-user-settings)

Summary [49](#summary-6)

Containerized microservices [50](#_Toc484430923)

Microservices [51](#microservices)

Containerization [52](#containerization)

Communication between client and microservices
[54](#communication-between-client-and-microservices)

Communication between microservices
[55](#communication-between-microservices)

Summary [57](#summary-7)

Authentication and authorization [58](#_Toc484430929)

Authentication [58](#authentication)

Issuing bearer tokens using IdentityServer 4
[59](#issuing-bearer-tokens-using-identityserver-4)

Adding IdentityServer to a web application
[59](#adding-identityserver-to-a-web-application)

Configuring IdentityServer [60](#configuring-identityserver)

Performing authentication [63](#performing-authentication)

Authorization [68](#authorization)

Configuring IdentityServer to perform authorization
[69](#configuring-identityserver-to-perform-authorization)

Making access requests to APIs [69](#making-access-requests-to-apis)

Summary [70](#summary-8)

Accessing remote data [71](#_Toc484430939)

Introduction to Representational State Transfer
[71](#introduction-to-representational-state-transfer)

Consuming RESTful APIs [72](#consuming-restful-apis)

Making web requests [72](#making-web-requests)

Caching data [79](#caching-data)

Managing data expiration [80](#managing-data-expiration)

Caching images [80](#caching-images)

Increasing resilience [81](#increasing-resilience)

Retry pattern [81](#retry-pattern)

Circuit breaker pattern [82](#circuit-breaker-pattern)

Summary [83](#summary-9)

Unit testing [84](#_Toc484430950)

Dependency injection and unit testing
[84](#dependency-injection-and-unit-testing)

Testing MVVM applications [85](#testing-mvvm-applications)

Testing asynchronous functionality
[86](#testing-asynchronous-functionality)

Testing INotifyPropertyChanged implementations
[86](#testing-inotifypropertychanged-implementations)

Testing message-based communication
[87](#testing-message-based-communication)

Testing exception handling [87](#testing-exception-handling)

Testing validation [88](#testing-validation)

Summary [89](#summary-10)
![](./media/image30.png)