# PS-Image Decoder

A Python tool for extracting PowerShell scripts hidden within PNG images using the Invoke-PSImage technique. This tool is particularly useful in digital forensics, malware analysis, and CTF (Capture The Flag) challenges where PowerShell scripts may be concealed within image files.

## Purpose

This tool is designed to:
- Decode PowerShell scripts that have been embedded in PNG images using the Invoke-PSImage technique
- Automatically save the extracted PowerShell scripts with a .ps1 extension
- Help security researchers and analysts investigate potentially malicious images
- Assist in CTF challenges where steganography techniques are used

## Features

- Extracts hidden PowerShell scripts from PNG images
- Automatically generates output files with .ps1 extension
- Supports optional length limitation for partial extraction
- Silent operation mode (no console output of extracted content)
- Simple command-line interface

## Usage

Basic usage:
```bash
python ps.py -i <input_image.png>
```

This will automatically create a PowerShell script file with the same name as the input image but with a .ps1 extension.

### Parameters

- `-i, --image`: Required. Path to the PNG image containing the hidden PowerShell script
- `-l, --length`: Optional. Maximum number of characters to extract

### Example

```bash
python ps.py -i evil_duck.png
```
This will create `evil_duck.ps1` containing the extracted PowerShell script.

## How It Works

The tool works by:
1. Reading the PNG image pixel by pixel
2. Extracting the least significant bits from the blue and green channels
3. Reconstructing the hidden PowerShell script from these bits
4. Saving the extracted script to a .ps1 file

## Requirements

- Python 3.x
- PIL (Python Imaging Library)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/ps-image-decoder.git
```

2. Install the required dependency:
```bash
pip install pillow
```

## Security Note

This tool is intended for legitimate security research, forensics analysis, and CTF challenges. Always exercise caution when dealing with potentially malicious PowerShell scripts and analyze them in a secure environment.
