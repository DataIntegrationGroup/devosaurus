---
sidebar_position: 1
---

# Why
    The New Mexico Water Data Initiative (NMWDI) has developed multiple core tools: 

    1. AMP API
    2. Weaver
    3. Data Integration Engine (DIE)
    
    Each of these tools serves a specific purpose and is designed to work together to provide a comprehensive set of data services to users.
    

## Why AMP API
    1. Provides a single point of access to all data in NMAquifer

## Why Weaver
    1. Modern component-based web application using React   
        1. Easy to maintain and extend
        2. Easy to deploy
    2. Accesses data from multiple sources and displays them in a single interface

    

## Why Data Integration Engine
    1. Open Source, Community Driven
    2. Technology stack we have experience with
    3. PIP installable package for easy deployment for users that want to use the engine directly
    4. Contains all the logic for data integration, data transformation, and data harmonization
    5. Can be used as a standalone package or as a library in a larger application
    6. Can be used to integrate data from multiple sources



## Weaver vs DIE
    Although Weaver and DIE are separate projects, they have overlapping functionality. This presents a challenge for 
    our development team to decide where to draw the line between the two projects. Here is a brief comparison of the two:

    #### DIE:

        1. service that can be used to integrate data from multiple sources
        2. written in Python. Can be used as a standalone package or as a library in a larger application
        3. contains all the logic for data access, transformation, and harmonization
    
    #### Weaver:

        1. Web application that uses a variety of services to integrate data from multiple sources and display it in 
        a single interface
        2. Written in React. Uses vite for compilation and bundling. Uses PrimeReact for UI components and styling

    #### Complication:
        Currently, a user can view data in Weaver but not download it and vice versa for DIE. We need to decide how to
        integrate the two projects so that a user can view and download data from the same interface!!!
