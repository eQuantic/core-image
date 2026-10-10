# eQuantic.Core.Image

Image manipulation for .NET on an engine of its own, with no native or third-party dependency.

> **Status: under construction.** The repository holds the build, the release and the working
> agreement. The engine arrives through the OpenSpec change `core-image-engine`, in the order below.
> Nothing has been published to nuget.org yet.

## Why another imaging library

The .NET options each bring something along: a native library to ship per platform (SkiaSharp,
libvips, Magick.NET) or a commercial license past a revenue threshold (ImageSharp). `eQuantic.Core.Image`
is managed code on the base class library alone, MIT, so it trims, compiles ahead of time, and runs
wherever .NET runs, from a Linux container to a browser through WebAssembly.

## What it will do

| Area | Scope |
|---|---|
| Read and write | JPEG (baseline and progressive), PNG, GIF (animated), BMP, WebP (lossless and lossy); the format told from the bytes, the size read from the header without decoding, a ceiling on pixels before anything is allocated |
| Metadata | EXIF orientation applied, EXIF, ICC and XMP read, kept or stripped on write |
| Transforms | Resize with the common modes (max, crop, pad, stretch) and kernels (nearest, bilinear, bicubic, Lanczos), crop, rotate, flip, a fluent pipeline |
| Web optimization | Format negotiated from `Accept`, widths for `srcset`, a blurred placeholder, sRGB output with the metadata stripped |
| Composition and effects | Overlay and watermark, blur, sharpen, grayscale, brightness, contrast, saturation |

## Packages

| Package | What it holds |
|---|---|
| [`eQuantic.Core.Image`](src/eQuantic.Core.Image/README.md) | The engine: the pixel buffers, the codecs, the transforms and the effects |

## Building

See [`CLAUDE.md`](CLAUDE.md) for the build, the tests, the release and the working agreement.

## License

[MIT](LICENSE)
