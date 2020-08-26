
# Google Summer of Code 2020 - Final Report

## CMake Build System

This is the final report for Google Summer of Code written by Ayush Chamoli.

## Summary

My aim for the summer was to finish CMake build scripts and implement other features in Synfig. This included small features (like adding support for internationalization and localization in CMake) to some major additions (like making installers using CPack).

Apart from this, I also planned to fix some CMake related bugs that were discovered during the GSoC period. 

You can take a look at the logs which I maintained for that particular period [here](https://forums.synfig.org/t/gsoc-2020-cmake-build-system/10963).


## Code

A list of all the commits I made related to the project can be found [here](https://github.com/synfig/synfig/commits?author=AYESDIE).

### Pull Requests 

**synfig**

- [#1224](https://github.com/synfig/synfig/pull/1224) - [CMake] Updated CMake script to change layout of build files.
  - [8d946dd](https://github.com/synfig/synfig/pull/1224/commits/8d946dd011e84511cce5b39da676e020fa23b00b) - Updated CMake script for bin and lib.
- [#1228](https://github.com/synfig/synfig/pull/1228) - [CMake] Update CMake script for /share and /etc.
  - [246c424](https://github.com/synfig/synfig/pull/1228/commits/246c424778cf17ebc59860e9f4238dd7d08efbd2) - Updated CMake script for share and etc. 
- [#1232](https://github.com/synfig/synfig/pull/1232) - Updated imagepath in case SYNFIG_ROOT is undefined. 
  - [c63f879](https://github.com/synfig/synfig/pull/1232/commits/c63f8790829695cbcf84345b50b8428fb4a5b1ec) - Updated imagepath in case SYNFIG_ROOT is undefined.
- [#1247](https://github.com/synfig/synfig/pull/1247) - Fixes for CMake build_images target. 
  - [a85cada](https://github.com/synfig/synfig/pull/1247/commits/a85cadae6212031d2b7173115982c0b5b1420281) - Fixes the build_images CMake target.
- [#1320](https://github.com/synfig/synfig/pull/1320) - Fix for no icon in Import Image Layer for CMake Build.
  - [21bb14c](https://github.com/synfig/synfig/pull/1320/commits/21bb14ce883a0a1821e76f61139488b82eb3f53f) - Fix for no icon in Import Image Layer for CMake Build.
- [#1462](https://github.com/synfig/synfig/pull/1462) - Generate l10n files from .po files. 
  - [99cde0a](https://github.com/synfig/synfig/pull/1462/commits/99cde0a7c6ddabd58e907af8b5bc382b5743daa5) - Generate l10n files from .po files
  - [dc3397b](https://github.com/synfig/synfig/pull/1462/commits/dc3397bab1b962521f3371bcf06a196648b59c70) - Custom gettext CMake function.
- [#1478](https://github.com/synfig/synfig/pull/1478) - build_images target's rebuilding behavior
  - [a16cd39](https://github.com/synfig/synfig/pull/1478/commits/a16cd39b7bf6f94e216c1c90a34779b3aa51ef33) - fix build_images target's rebuilding behavior
- [#1484](https://github.com/synfig/synfig/pull/1484) - Resource management of CMake build.
  - [9370119](https://github.com/synfig/synfig/pull/1484/commits/93701191f5c3e24f84c330cdcfc6459d9902d55a) - Changes for CMake related app resource path.
- [#1491](https://github.com/synfig/synfig/pull/1491) - Changes for appveyor build using CMake and ninja.
  - [ec68c0a](https://github.com/synfig/synfig/pull/1491/commits/ec68c0ac35255aaa5de94f48a6418771a9a22510) - Windows related changes
  - [3c5438c](https://github.com/synfig/synfig/pull/1491/commits/3c5438c75598cd2756729eaddf6adf288481078b) - Fixed MLT Path added different dependency for MSYS2 builds.
  - [ff40532](https://github.com/synfig/synfig/pull/1491/commits/ff4053293e4593865cb983238ce0be3108c8cbf8) - Changes for CMake MSYS builds.
- [#1500](https://github.com/synfig/synfig/pull/1500) - Different CMake builds based on CMAKE_BUILD_TYPE.
  - [c323060](https://github.com/synfig/synfig/pull/1500/commits/c3230601682226b0b0d009a31adbaa6db809fa0d) - Different CMake builds based on CMAKE_BUILD_TYPE.
- [#1501](https://github.com/synfig/synfig/pull/1501) - Copy plugins, brushes and sounds to the appropriate place in CMake build.
  - [836b46a](https://github.com/synfig/synfig/pull/1501/commits/836b46a978c0c0abbc7457fc0a7f320a7f045f40) - Copy plugins, brushes, sounds and ui to /share/synfig in CMake builds
  - [d007f97](https://github.com/synfig/synfig/pull/1501/commits/d007f97f889425abc9f66461f6d8ab0114b9b732) - Added a custom function for intltool_merge
    - Moved `/cmake/Modules/SynfigGettext.cmake` to `/cmake/SynfigGettext.cmake`.
    - Moved `/cmake/Modules/SynfigFindgGit.cmake` to `/cmake/SynfigFindGit.cmake`.
    - Fixed an issue where `build_pofiles_synfigstudio` wasn't building.
- [#1519](https://github.com/synfig/synfig/pull/1519) - CPack: .deb package
  - [60af052](https://github.com/synfig/synfig/pull/1519/commits/60af052d2f63bb503f6899b412c0db7d21911454) - .deb package
    - Added a basic CPackConfig.cmake script and PACKAGING.md to generate .deb packages.
    - Updated `SYNFIG_INTLTOOL_MERGE` to account for .desktop.in files.
    - Made changes to move icon to the specified location in cmake builds.
    - Added dependencies on `synfig_bin` and `synfigstudio` to make building process easier.
- [#1581](https://github.com/synfig/synfig/pull/1581) - Setting up VERSIONINFO resource for CMake Windows builds.
  - [9b4afe8](https://github.com/synfig/synfig/pull/1581/commits/9b4afe8469a468e08a8476370e33323526f68c63) Setting up VERSIONINFO resource for CMake Windows builds.
- [#1582](https://github.com/synfig/synfig/pull/1582) - CPack NSIS Installer.
  - [783a2dd](https://github.com/synfig/synfig/pull/1582/commits/783a2dd427c0a08292e2b86eabe3c4b8611c2da4) - CMake NSIS Installer
- [#1595](https://github.com/synfig/synfig/pull/1595) - Fixed Magick NoEncodeDelegateForThisImageFormat issues on appveyor build.
  - [7538ae5](https://github.com/synfig/synfig/pull/1595/commits/7538ae5b9de8f0fa9e880512f1910dbcda924d17) - Fixed Magick NoEncodeDelegateForThisImageFormat issues on MSYS build
- [#1644](https://github.com/synfig/synfig/pull/1644) - Removed README-CMake.md and linked CMake documentation in README.md.
  - [7ab6d6d](https://github.com/synfig/synfig/pull/1644/commits/7ab6d6d3f54e7eff4534cbed63b13dee6854ca4b) - Removed README-CMake.md and linked CMake documentation in README.md

**synfig-docs-dev**
- [#53](https://github.com/synfig/synfig-docs-dev/pull/53) - [CMake] Added documentation for CMake.
  - [b498507](https://github.com/synfig/synfig-docs-dev/pull/53/commits/b4985079f505248c353d86886292f7174e273d8b) - Added documentation for CMake.
- [#58](https://github.com/synfig/synfig-docs-dev/pull/58) - Fixed CPack packaging documentation.
  - [b93a9d7](https://github.com/synfig/synfig-docs-dev/pull/58/commits/b93a9d7f2f4f7710bd0fe0433f26e43900ae6eb9) - Fixed cpack packaging documentation.
  
## What's Left 

The following tasks are still left:
- [#1630](https://github.com/synfig/synfig/pull/1630) - [CMake] MacOS app and DMG installer.
- [#1646](https://github.com/synfig/synfig/pull/1646) - Changes for successful CMake configuration using MSVS 2019 and vcpkg.

## Experience

The past few months have been great working with Synfig! I learned a lot of new things about various technologies and gained a lot of exposure. I had been a bit active in open source before, but working with Synfig gave me a far more better experience in the open source world than what I had been involved in previously. I still plan to contribute to Synfig after GSoC ends, and possibly learn a lot more!
