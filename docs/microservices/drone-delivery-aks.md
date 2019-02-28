---
title: Microservices reference implementation for Azure Kubernetes Service
description: This reference implementation illustrates best practices for a microservices architecture
author: MikeWasson
ms.date: 02/26/2019
ms.topic: guide
ms.service: architecture-center
ms.subservice: reference-architecture
ms.custom: microservices
---

# Microservices reference implementation for Azure Kubernetes Service

Microservices have become a popular architectural style for building cloud applications that are resilient, highly scalable, independently deployable, and able to evolve quickly. To be more than just a buzzword, however, microservices require a different approach to designing and building applications.

In this set of articles, we explore how to build and run a microservices architecture on Azure. Topics include:

- [Interservice communication](./interservice-communication.md)
- [API design](./api-design.md)
- [API gateways](./gateways.md)
- [Data considerations](./data-considerations.md)
- [Design patterns](./design-patterns.md)

## Prerequisites

Before reading these articles, you might start with the following:

- [Introduction to microservices architectures](./introduction). Understand the benefits and challenges of microservices, and when to use this style of architecture.
- [Using domain analysis to model microservices](./domain-analysis.md). Learn a domain-driven approach to modeling microservices.

## Reference implementation

To illustrate best practices for a microservices architecture, we created a reference implementation that we call the Drone Delivery application. This implementation runs on Kubernetes using Azure Kubernetes Service (AKS). You can find the reference implementation on [GitHub][drone-ri].

![Architecture of the Drone Delivery application](./images/drone-delivery.png)

## Scenario

​Fabrikam, Inc. is starting a drone delivery service. The company manages a fleet of drone aircraft. Businesses register with the service, and users can request a drone to pick up goods for delivery. When a customer schedules a pickup, a backend system assigns a drone and notifies the user with an estimated delivery time. While the delivery is in progress, the customer can track the location of the drone, with a continuously updated ETA.

This scenario involves a fairly complicated domain. Some of the business concerns include scheduling drones, tracking packages, managing user accounts, and storing and analyzing historical data. Moreover, Fabrikam wants to get to market quickly and then iterate quickly, adding new functionality and capabilities. The application needs to operate at cloud scale, with a high service level objective (SLO). Fabrikam also expects that different parts of the system will have very different requirements for data storage and querying. All of these considerations lead Fabrikam to choose a microservices architecture for the Drone Delivery application.

> [!NOTE]
> For help in choosing between a microservices architecture and other architectural styles, see the [Azure Application Architecture Guide](../guide/index.md).

Our reference implementation uses Kubernetes with [Azure Kubernetes Service](/azure/aks/) (AKS). However, many of the high-level architectural decisions and challenges will apply to any container orchestrator, including [Azure Service Fabric](/azure/service-fabric/).

<!-- links -->

[drone-ri]: https://github.com/mspnp/microservices-reference-implementation

## Next steps

- [View the code and deploy the application][drone-ri] (GitHub).
- Learn about using domain analysis to [model microservices](./domain-analysis.md).
- Learn about [interservice communication](./interservice-communication.md) for microservices.