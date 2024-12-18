# Dockerfile Bug: Missing requirements.txt
This repository demonstrates a common error in Dockerfiles: attempting to use a file that hasn't been added to the image yet.  The `COPY` instruction fails because `requirements.txt` is not found in the build context.

## Bug Description
The provided Dockerfile attempts to install Python packages using `pip3 install -r requirements.txt` before copying `requirements.txt` into the image. This leads to a build failure.

## Solution
The corrected Dockerfile ensures `requirements.txt` is copied *before* the `pip3 install` command is executed.