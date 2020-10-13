# libprotobuf-mutator-asn1

## Overview
libprotobuf-mutator-asn1 is a library that uses [https://github.com/google/libprotobuf-mutator](libprotobuf-mutator)
to generate inputs that can exercise ASN.1 parsers, particularly DER parsers.
By using a structurally-aware approach that is able to encode valid lengths,
inputs are able to more quickly exercise interesting code paths.

In addition to structurally- and syntactically-valid DER, it supports generating
BER inputs as well as generating random data, ensuring coverage is not lost
compared to classic fuzzers.

## X.509 Fuzzing
In addition to the generic ASN.1 fuzzer, this library can also generate
X.509 certificates in a structure-aware fashion. This is to facilitate deeper
fuzzing of certificate chain parsing, building, and validation engines, by
creating certificates and certificate chains that are structurally-valid, but
which can contain fuzzed data (e.g. arbitrary extensions)

## Usage
This project is still a work-in-progress to separate as a standalone library.
Until that work is completed, example usage within OSS-fuzz can be seen at
https://github.com/google/oss-fuzz/commit/e15b72d833dd5c30f4cd4aed2ba06e64011ce73d

## Disclaimer
This is not an officially supported Google product
