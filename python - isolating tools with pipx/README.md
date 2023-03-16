Sample project showcasing how to isolate dependencies when building Docker images:

- development tools (`poetry`, `virtualenv`) installed in isolated environments using `pipx`.
- all dependencies installed inside a virtual environment for the app

### Running

Clone the repo, navigate to this folder and run `make image`. You can inspect the image by doing:

- `docker run video`: should print the numpy array, a sign the code is running
- `docker -it video /bin/bash`: shell into the container; do `pip show numpy` to check where numpy is getting installed.
