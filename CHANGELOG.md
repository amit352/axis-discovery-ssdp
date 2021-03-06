# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/) and this project adheres to [Semantic Versioning](http://semver.org/).

## [Unreleased]

## [5.0.0] - 2017-12-22

### Changed

- The property `macAddress` on `Device` changed type from `string | undefined` to `string`. Devices without a MAC address are now omitted from search results.

## [4.1.0] - 2017-11-27

### Added

- The option to specify a custom implementation of a HTTP client, where the default is based on [Request](https://www.npmjs.com/package/request). This can be useful if discovery is required in an Electron application where one wish to benefit from the proxy configuration provided by using Electron's [net.request](https://electronjs.org/docs/api/net).

## [4.0.2] - 2017-10-14

### Fixed

- Issue where exception was thrown when received message didn't specify MAC address

## [4.0.1] - 2017-07-06

### Fixed

- Issue where socket listeners remained alive when discovery was stopped

## [4.0.0] - 2017-07-04

### Added

- Support for enabling logs using [debug](https://github.com/visionmedia/debug)

### Removed

- Support for Node.js v5 (v6 is LTS)

## [3.0.0] - 2017-06-26

### Changed

- Renamed `Device.serialNumber` to `Device.macAddress`. In most situations they are still the same, but the exceptions are the Axis products which bundle multiple physical devices into a single casing with a shared network interface. Because of the shared network interface they also share the same MAC address. This package is opinionated in that even though the devices via SSDP (UPnP) call the property _serial number_, it actually is a _MAC address_ and should be named accordingly.

## [2.0.0] - 2017-06-24

### Added

- [#2](https://github.com/FantasticFiasco/axis-discovery-ssdp/issues/2) - Calling `Discovery.stop()` stops listening for SSDP advertisements

### Changed

- Replaced `null` with `undefined` according to [TypeScript guidelines](https://github.com/Microsoft/TypeScript/wiki/Coding-guidelines#null-and-undefined)

## [1.0.2] - 2017-01-26

### Fixed

- [#40](https://github.com/FantasticFiasco/axis-discovery-ssdp/issues/40) - Calling `Discovery.search()` didn't trigger a new search

## [1.0.1] - 2016-12-06

### Fixed

- Updated `README.md` in package

## [1.0.0] - 2016-12-04

### Added

- Support for discovering [Axis Communications](http://www.axis.com/) devices on the network using SSDP (UPnP)
