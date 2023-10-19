# BrowseTerm Socket
WebSocket server that connects to SSH Servers and provides an socket based SSH Interface to SSH Servers. Can be used by Web Based Terminal Renderers like xterm.js.

# How to build
Run the following command to build the image
```
make build
```

# How to push
Run the following command to push to docker repository
```
make push
```
NOTE: Push only works for people who know the password or have access to PAT.

# How to build and push
Run the following command to build the image and push to repository
```
make buildpush
```
NOTE: Push only works for people who know the password or have access to PAT. Therefore, this step also requires people to know the password or have access to PAT.

# How to run locally
- Requirements:
  - Docker needs to be installed
  - Create a virtual environment and hit: `pip install -r requirements.txt`.

To run locally outside the docker container you can do the following:
1. Create the test ssh container:
    ```
    make runtestsshcontainer
    ```
    This will build the container, run it on `0.0.0.0:2223`.

2. Open up a terminal and run the python socket server:
    ```
    python app.py
    ```
    This will run our socket server on `0.0.0.0:8000`

3. Open up another terminal and run the test client:
    ```
    python test_client/test_client_server.py
    ```
    This will run our test_client on `0.0.0.0:8375`.
    Open the browser and type `0.0.0.0:8375` to view the client.


# BUGS:
1. Fix the top and apt-install command. Read output without having to hit enter.


# Concerns
1. Scaling websockets.
2. Securing websockets with SSL.
3. Securing websockets endpoint with AUTH.
4. Deploying locally for test.
5. Deploying on k8s