name: CI-CD

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - name: Install dependencies
      run: npx yarn
    - name: Build
      run: npx yarn build
    - name: Upload artifact
      uses: actions/upload-artifact@v3
      with: 
        name: assets
        path: dist

[![CI-CD](https://github.com/fernkomoyo/codioCourse/actions/workflows/CI-CD.yml/badge.svg)](https://github.com/fernkomoyo/codioCourse/actions/workflows/CI-CD.yml)
