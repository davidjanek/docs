---
layout: page_toc
title: "Change Log"
active_item: "changelog"
---

# Change Log
All notable changes to this project will be documented in this file.

## Mergado Apps 0.2.3
- 2016-06-29

### Added
- List of categories available on [Heureka](http://docs.mergado.apiary.io/#reference/heureka/heureka-categories).
- Google Analytics for all [eshop data](http://docs.mergado.apiary.io/#reference/google/analytics/eshop-data).
- List of supported [XML formats](http://docs.mergado.apiary.io/#reference/0/xml-formats/eshop-data) in Mergado.

## Mergado Apps 0.2.2
- 2016-06-01

### Added
- Mergado now calls app's constructor/destructor hooks when enabling or disabling an app, respectively (see [hooks]({{ site.baseurl }}/apps/app-hooks.html)).
- API endpoints for [tasks management](http://docs.mergado.apiary.io/#reference/management/tasks).
- API endpoints for various [logs and actions](http://docs.mergado.apiary.io/#reference/management/logs).
- Support `filter_by` query string parameter in [statistics](http://docs.mergado.apiary.io/#reference/statistics/products/statistics-of-all-products).
- Allow POST for requesting [products' statistics](http://docs.mergado.apiary.io/#reference/statistics/products/statistics-of-all-products-using-post).
- Added more information (about connection with shopping services) to the _[eshop info](http://docs.mergado.apiary.io/#reference/management/eshops/show-eshop-info)_ endpoint.
- Added endpoint for listing [user's notifications](http://docs.mergado.apiary.io/#reference/management/notifications/get-users-notifications).

### Fixed
- Parameter `fields` in API of statistics.
- Support the creation of the rule type `hiding` (hiding of products).

## Mergado Apps 0.2.1
- 2016-05-18

### Added
- API endpoints for [notifications](http://docs.mergado.apiary.io/#reference/management/notifications).
- API endpoints for [XML feed audits](http://docs.mergado.apiary.io/#reference/feed-audits).
- API endpoint for [querying products](http://docs.mergado.apiary.io/#reference/management/products/query-products).

### Changed
- The field `data` in product collections was returning input data. Now it returns the output data and the input data are listed in a new field `input_data`.
- Mergado App IFRAME API (*Maia*) now has two new methods: `startDownload` and `openWindow`. Also a bug was fixed when calling `tellHeight` method repeatedly.

## Mergado Apps 0.2.0
- 2016-05-04

### Added
- API endpoints for [statistics](http://docs.mergado.apiary.io/#reference/statistics).
- API endpoints for [product management](http://docs.mergado.apiary.io/#reference/management/products).
- API endpoint for [Google Analytics](http://docs.mergado.apiary.io/#reference/google).

### Fixed
- Creating or updating a rule did not update indicator of "change" in project, i.e. when rules were processed in a project, they were all skipped and the rule was not applied at all.

## Mergado Apps 0.1.2
- 2016-04-21

### Added
- API endpoint `GET /shops/<id>/info/`.
- API endpoint `GET /projects/<id>/info/`.
- Implemented a new communication protocol for [rule definitions]({{ site.baseurl }}/apps/defining-new-rules.html) by applications.
- New fields `is_movable`, `is_editable` and `is_pausable` were added to the rule collection.

### Changed
- When creating new rules by `POST /projects/<id>/rules/`, it is now possible to include the field `queries` which assigns queries to the rule in one request. If the field is not included, the query returning all products is automatically assigned.
- The field `deletable` in the rule collection was renamed to `is_deletable`.

### Fixed
- Server error when creating new `bidding` rule with empty `data` field (issue [#12](https://github.com/mergado/mergado-apps/issues/12)).
- Server error when creating query that already exists (Issue [#11](https://github.com/mergado/mergado-apps/issues/11)).

## Mergado Apps 0.1.1
- 2016-04-06

### Added
- New API endpoints `PATCH /rules/<id>/queries/` and `DELETE /rules/<id>/queries/<id>/` let you assign and retract queries from rules.

### Fixed
- Correctly update a rule when `PATCH /rules/<id>/` with `data` field is issued.
- When creating or updating a rule or a variable, the API returns 400 Bad Request if the associated element does not exist.

## Mergado Apps 0.1.0
- 2016-03-23

### Added
- Mergado API ([app.mergado.com/api](https://app.mergado.com/api)).
- API documentation ([docs.mergado.apiary.io](http://docs.mergado.apiary.io/)).
