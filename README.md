# FileTypeDetector
Files type detector based on file name extension or file content (binary content).

[![Composer package](http://xn--e1adiijbgl.xn--p1acf/badge/wapmorgan/file-type-detector)](https://packagist.org/packages/wapmorgan/file-type-detector)
[![Latest Stable Version](https://poser.pugx.org/wapmorgan/file-type-detector/v/stable)](https://packagist.org/packages/wapmorgan/file-type-detector)
[![Total Downloads](https://poser.pugx.org/wapmorgan/file-type-detector/downloads)](https://packagist.org/packages/wapmorgan/file-type-detector)
[![Latest Unstable Version](https://poser.pugx.org/wapmorgan/file-type-detector/v/unstable)](https://packagist.org/packages/wapmorgan/file-type-detector)
[![License](https://poser.pugx.org/wapmorgan/file-type-detector/license)](https://packagist.org/packages/wapmorgan/file-type-detector)

1. Usage
2. Installation
3. Supported formats

# Usage

## File Type detection

- Detection by filename: `detectByFilename(...filename...)`
- Detection by content: `detectByContent(...filename...)`

Example:

```php
$type = wapmorgan\FileTypeDetector\Detector::detectByFilename($filename);

// $type will contain file type as an array like this:
// array(
//   Detector::AUDIO,
//   Detector::MP3
// )
// In case of failure it will contain `false`.


$type = wapmorgan\FileTypeDetector\Detector::detectByContent('file-without-extension');
// or
$type = wapmorgan\FileTypeDetector\Detector::detectByContent(fopen('http://somedomain/somepath', 'r'));
```

## Mimetype generation

To use correct mimetype for file there is `getMimeType($type)` function.

```php
$mime = wapmorgan\FileTypeDetector\Detector::getMimeType($type[1]);
// or
$mime = wapmorgan\FileTypeDetector\Detector::getMimeType(wapmorgan\FileTypeDetector\Detector::MP3);
```

# Installation
Install package via composer:
```
composer require wapmorgan/file-type-detector
```

# Supported formats

| Format            | In code                    |
|-------------------|----------------------------|
| **Audio**         | **Detector::AUDIO**        |
| .aac              | Detector::AAC              |
| .amr              | Detector::AMR              |
| .flac             | Detector::FLAC             |
| .ogg              | Detector::OGG              |
| .mp3              | Detector::MP3              |
| .m3u              | Detector::M3U              |
| .wav              | Detector::WAV              |
| .wma              | Detector::WMA              |
| **Video**         | **Detector::VIDEO**        |
| .3gp              | Detector::_3GP             |
| .asf              | Detector::ASF              |
| .avi              | Detector::AVI              |
| .flv              | Detector::FLV              |
| .m4v              | Detector::M4V              |
| .mkv              | Detector::MKV              |
| .mov              | Detector::MOV              |
| .mpeg, .mpg       | Detector::MPEG             |
| .wmv              | Detector::WMV              |
| **Images**        | **Detector::IMAGE**        |
| .jpeg, .jpg       | Detector::JPEG             |
| .bmp              | Detector::BMP              |
| .gif              | Detector::GIF              |
| .png              | Detector::PNG              |
| .tiff             | Detector::TIFF             |
| .psd              | Detector::PSD              |
| **Archives**      | **Detector::ARCHIVE**      |
| .bz2              | Detector::BZIP2            |
| .gz               | Detector::GZIP             |
| .xz               | Detector::LZMA2            |
| .7z               | Detector::_7ZIP            |
| .cab              | Detector::CAB              |
| .jar              | Detector::JAR              |
| .rar              | Detector::RAR              |
| .tar              | Detector::TAR              |
| .zip              | Detector::ZIP              |
| **Databases**     | **Detector::DATABASE**     |
| .mdb              | Detector::MDB              |
| .odb              | Detector::ODB              |
| **Documents**     | **Detector::DOCUMENT**     |
| .doc              | Detector::DOC              |
| .docx             | Detector::DOCX             |
| .html             | Detector::HTML             |
| .odt              | Detector::ODT              |
| .pdf              | Detector::PDF              |
| .rtf              | Detector::RTF              |
| .txt              | Detector::TXT              |
| .xml              | Detector::XML              |
| **Font-faces**    | **Detector::FONT**         |
| .otf              | Detector::OTF              |
| .ttf              | Detector::TTF              |
| **Executables**   | **Detector::APPLICATION**  |
| .apk              | Detector::APK              |
| .com              | Detector::COM              |
| .exe              | Detector::EXE              |
| **Presentations** | **Detector::PRESENTATION** |
| .ppt              | Detector::PPT              |
| .pptx             | Detector::PPTX             |
| .odp              | Detector::ODP              |
| **Spreadsheets**  | **Detector::SPREADSHEET**  |
| .ods              | Detector::ODS              |
| .xls              | Detector::XLS              |
| .xlsx             | Detector::XLSX             |
