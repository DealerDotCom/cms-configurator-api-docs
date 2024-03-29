# Release Notes
All notable releases to this project will be documented in this file. 
## [12/**/2023]
**Removed**
Removed keywords from Metadata functionality.

## [6/1/2023] 
**Updated**
* Increased cap on created pages.

## [4/6/2023] 
**Updated**
* PATCH mechanism now supports pageTitles

## [3/21/2023]
**Added**
* Soft cap on created pages. 
* Service Rate limiting handling
* page per site limitations
* PATCH mechanism for updating content/metadata 
* Content Locale validation with *x-disable-locale-validation* header to bypass 

## [3/12/2023]
**Updated**
* API key authentication to use query instead of scan
* Release notes and Documentation
**Added**
* X-CoxAuto-Correlation-Id tracing header
* POST mechanism
* DELETE mechanism 

## [2/14/2023]
**Added**
* API key authentication
* Release notes and Documentation
* Stood up deploy mechanism and terraform 
* new POC end point to communicate with CMS-Configurator backing service
