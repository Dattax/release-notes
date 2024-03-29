# Release Notes

<!-- MarkdownTOC autolink="true" bracket="round" -->

- [2019 October 17: Bug fixes and regular maintenance for Go](#2019-october-17-bug-fixes-and-regular-maintenance-for-go)
- [2019 October 9: More UI improvements](#2019-october-9-more-ui-improvements)
- [2019 October 7: New Metrics Panel and New Go Center Look](#2019-october-7-new-metrics-panel-and-new-Go-Center-look)
- [2019 September 19: SEO improvements](#2019-september-19-seo-improvements)
- [2019 September 10: Checksum database support in GoCenter](#2019-september-10-checksum-database-support-in-gocenter)
- [2019 September 3: Beginning to build a Go Modules Score](#2019-september-3-beginning-to-build-a-go-modules-score)
- [2019 August 27: Discovery process updates](#2019-august-27-discovery-process-updates)
- [2019 July 23: Released GoCenter module page](#2019-july-23-released-gocenter-module-page)
- [2019 June 12: Display module information in search results](#2019-june-12-display-module-information-in-search-results)
- [2019 June 6: Improved search functionality](#2019-june-6-improved-search-functionality)
- [2019 May 24: Go version updates](#2019-may-24-go-version-updates)
- [2019 April 26: Improve module metadata and search](#2019-april-26-improve-module-metadata-and-search)
- [2019 March 27: Enhanced automatic inclusion of Go modules](#2019-march-27-enhanced-automatic-inclusion-of-go-modules)
- [2019 March 20: Inclusion, discovery, validation](#2019-march-20-inclusion-discovery-validation)
- [2019 March 14: Updated logic for generating mod files](#2019-march-14-updated-logic-for-generating-mod-files)
- [2019 March 9: Fixed incompatibility](#2019-march-9-fixed-incompatibility)
- [2019 February 7: Optimized discovery and support for Jenkins](#2019-february-7-optimized-discovery-and-support-for-jenkins)
- [2019 January 28: GA](#2019-January-28-ga)

<!-- /MarkdownTOC -->

## 2019 October 17: Bug fixes and regular maintenance for Go
This week we made some improvements to SEO and fixed a few other items:
* We adjust the weights for criteria for Go Module scoring
* Upgraded Kubernetes to patch security issue
* Metadata service to trigger lookup calls for new module versions against gosumdb.
* Fixed runnable Go version

## 2019 October 9: More UI improvements
Lots of small changes to the Go Center UI. We've added minor improvements to all the content that we released earlier this month. Fixes include:
* Fixed source location discovery and added API to fix data
* Fixed runnable go version
* Added SEO keywords to header
* Stats calculated text alignment
* Updated autosuggest styles
* Updated homepage Image
* Discovery ignoring tags with + suffix

## 2019 October 7: New metrics panel and new Go Center look
A new version of GoCenter was released today. Apart from the look and feel changes, there is a new metrics panel that will  help module authors and users access additional metadata to make better decisions around which modules to use. Check it out - https://search.gocenter.io/stats

Other updates included a new improved homepage image and:
* Top bar has been changed from green to black to match the new unified experience look and feel 
* The navigation menu has been expanded to include versions and metrics visible in the UI from the start
* White information bar includes new metrics data including license information
* A blog link has been added to the top bar.

## 2019 September 19: SEO improvements
We've been improving the SEO experience with changes to the content and UI
 *	Added a new CLI version
 *	GoCenter search description update for SEO
 *	Scoring tab updates

## 2019 September 10: Checksum database support in GoCenter
In this release, we started supporting the checksum database by proxying sum.golang.org. So if you upgraded Go to 1.13 and have the proxy already set to https://gocenter.io, then the sumdb requests from the Go client will also be served by gocenter.io. As part of this release, we also:
 *	modified package.json
 *	Metrics tab update
 *	Added get module names API
 
 ## 2019 September 3: Beginning to build a Go Modules Score
 On this release, we started working on the back-end needed for Go Module scores. Updates include:
 * We also made updates to the metrics panel
 * Create job to compute modules score factors and scores
 * Fixed Jenkins files and graceful shutdown
 
## 2019 August 27: Discovery process updates
In this release, we fixed a few issues regarding the discovery request process. Both discovery and getModules API will validate if module name is declared in the go.mod file of a tag – if it is compatible with the project being checked. If they are not compatible, the tag will be ignored. Other improvements on this release include:
 *	do a lookup on Artifactory sumdb virtual repo during metadata update.
 *	Check git url before trying to fetch tags
 *	Fix github link for pseudo versions

## 2019 July 23: Released GoCenter module page
In this release, GoCenter has:
* Introduced a module page. As a one-stop central Go modules repository, GoCenter now provides more module information to developers to decide whether to use this module as a dependency in a project. Each module in GoCenter now has five tabs to show information:
  * README: Developers care about documentation, so the first page you land on is the README documenting the module
  * Mod file: This tab shows the contents of the `go.mod` file or, if the module has not adopted Go modules yet, GoCenter will  recommend a mod file based on `go mod tidy` for the latest version of the module available in GoCenter.
  * Dependencies: This tab shows all of the module’s dependencies in a dependency tree format.
  * Used by: This tab shows which other projects use the selected module
  * Versions: This tab shows all the versions that GoCenter knows about, and has a copy of, ready to serve to developers.
* Changed the way Go modules are resolved. If the module isn’t in GoCenter, it will get the module from the source for you. This feature limits the number of HTTP/404 responses and means developers no longer need any additional tools to get all their public modules from GoCenter.
* Updated the `Set Me Up` page to include instructions for Windows PowerShell and the traditional Windows terminal.

## 2019 June 12: Display module information in search results
In this release, module metadata will be displayed as part of search results. Other fixes that came out today include:
*	Deep processing when shallow processing times out.	
*	Added module update retries		
*	Log expired locks		
*	Fixed virtual repo composition

## 2019 June 6: Improved search functionality
In this release, GoCenter has enriched the search functionality which includes most relevant Go modules in search results. Other updates include:
*	Ignore build constraint validation failure
*	Fixed elastic json escape bug
*	Added support to Artifactory 6.10.x
*	Added support to modules with .go in their names
 
## 2019 May 24: Go version updates
This month we’re continuing to make updates to Go Center that incorporate changes from Go 1.12. These include:
*	store/fetch go.mod-public/suggested in bucket and server via rest when invoked
*	gomodinittidy flow	store/fetch go.mod-public/suggested in bucket and server via rest when invoked
*	gomodinittidy flow
*	Fixed module indexing issues		
*	Init cache provider for metadata service
*	module metrics in module status, readme from art

## 2019 April 26: Improve module metadata and search
The focus here was on adding module metadata services and improving the search experience. Updates include:
*	Initial version source location metadata job			
*	Changed elastic client and added new source location metadata		
*	Added metrics daos				
*	Created metadata microservice		
*	Elastic added to devenv		
*	Removed plus suffixed tags from missing		
*	Changed elastic client and added new source location metadata

## 2019 March 27: Enhanced automatic inclusion of Go modules 
In this release, GoCenter has enhanced the automatic inclusion of Go modules
* GoCenter will now automatically attempt to include missing Go modules that were requested at least once
* This means that if a user tries to retrieve a dependency from GoCenter, but receives a 404 error (“Not Found”) because the module does not yet exist in GoCenter, a background process in GoCenter will eventually try to include that module through the [Inclusion Request process](https://github.com/jfrog/gocenter/wiki/How-GoCenter-Works#inclusion-process). 
* This feature will enhance the user experience of GoCenter as a Go proxy by reducing the occurrence of 404 errors in your builds.

## 2019 March 20: Inclusion, discovery, validation
Lots of Bug fixes. Inclusion, discovery, validation. A few other updates over the last two weeks include:
* Init shared cache provider for discovery microservice
* Fixed missing dependency injection
* Added version existence check, module name and version decoding Added inclusion request rules caching and github quota check * Initial inclusion request refactoring 
* Event validation rules 
* Create job structure initial version
* Added version existence check, module name and version decoding
* Fixed go.sum file

## 2019 March 14: Updated logic for generating mod files 
In this release, GoCenter has changed the logic of mod files generation. 
* GoCenter will no longer generate a populated go.mod file for Go projects that haven’t yet opted into modules and do not yet contain a go.mod file. Prior to this release, GoCenter was using a different approach to produce missing go.mod files, to achieve optimal reproducibility. However, after further discussion with the Go community, and considering that the initial approach may cause the go.mod file’s checksum to be different from what may have been recorded in a project’s go.sum before using GoCenter, GoCenter will now generate empty go.mod files for Go projects that haven’t yet opted into modules.
* As part of this release, go.mod files that were previously generated by GoCenter will be converted to be consistent with this new behavior.
* For Go projects that already have go.mod files, GoCenter will continue to keep these .mod files unchanged when processing them to be included in GoCenter.

## 2019 March 9: Fixed incompatibility
This release focused on bug fixes and included fixing scenario incompatibility issues. Updates:
* Fix double +incompatible versions creation
* Initial inclusion request refactoring		
* Event validation rules		
* Added module list query

## 2019 February 7: Optimized discovery and support for Jenkins
We updated and fixed some core features. We focused on optimized discovery. More Updates include:
* Converted production cluster from zonal to regional
* Added retry mechanisms during processing
* Check for max number of tags before getting another page of tags
* Add regional stage and prod clusters support for Jenkins deploy		
* Fixed feature pipeline 
* Introduced retries and checks for CLI timeouts
* Updated caddy_helm_pkg_feat.sh and add debug for other Jenkins files
* Sdd regional stage and prod clusters support for Jenkins deploy		
* Trigger CI pipeline

## 2019 January 28: GA
GoCenter.io goes live!
* Basic ability to search for modules
* Basic ability to request new modules be added to GoCenter
* Basic ability to determine the status of a module/version
*	New CLI version
*	Updated the UI
*	Created helper to fix Artifactory mod files
*	Updated main view mobile layout
