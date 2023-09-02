# Immutable Wasm Linux using Flatcar

This repo is a start on building a set of dev and prod Flatcar "sysext" layers that contain important and not-so-important WebAssembly and Wasm Component Model tools to both creat and test and also to host using an immutable but updateable Flatcar image. Other immutable distributions that use .raw files and ignition files may be able to use these approaches as well.

All .raw layers are built using the recipes in https://github.com/squillace/sysext-bakery. **CAUTION**: Having been assembled for a presentation, they are not supported and in fact exhibit large errors, typos, and so on -- they are meant ONLY as examples that will change. I will continue to update them and accept new ones in PRs, but my hope is that the Flatcar community will eventually accept cleaned up versions back into the sysext repo whence they came.

## Contents

The dev-flatcar folder contains a script that, given a pointer to a local Flatcar production image `.img` file, will boot that file and use the ignition.json file in that directory to install any layers and lock down the image with that content on first boot. Afterwards, the image is entirely immutable -- with some limits as outlined in the Flatcar documentation.