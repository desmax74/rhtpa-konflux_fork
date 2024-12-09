# RHTPA Konflux

## Directory structure

- **components**: Contains all repositories we need to build the whole RHTPA product

## Development

Clone this repositoy and init the submodules:

```shell
git submodule init
git submodule update
```

### Helm Chart

The values used for the Helm Chart is stored at the file `.helm.env`

For being able to locally build the Helm Chart you can do:

```shell
podman build -t trustify-helm-charts --build-arg-file .helm.env -f Dockerfile.helm .
```

Then get the helm using:

```shell
podman cp $(podman create --name helm-download trustify-helm-charts):/tmp/trustify-helm-charts . && podman rm helm-download
```

You should see a directory `trustify-helm-charts` being created and contains the Helm Chart
