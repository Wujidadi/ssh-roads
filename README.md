# SSH Roads Shell Script

## Usage

```sh
cp .env.example .env # Then edit .env with your desired values
cp servers.example servers # Then edit servers with your desired values
./roads
```

It is recommended to add this project directory to your `PATH` environment variable, so you can call `roads` globally (Make sure only the `roads` file in the directory has execute permission to avoid accidentally running other files)
```sh
export PATH=$PATH:$(pwd)
roads
```

## Configuration

### `.env`

* Environment variables, can store sensitive information such as passwords

### `servers`

* Content is formatted as a table separated by `|`
* All columns are left-aligned by default; except for the last column (`comment`), you can add spaces to the right of the value string before the separator `|` for alignment
* The meaning and order of each column can be found in `servers.example`
* Connection type (`conn_type`) supports the following values:
  - `password`: Connect using password, calls `sshexp` to perform SSH connection via expect (Expect Tcl tool required)
  - `gcp`: GCP, connects using the `gcloud` command (GCP CLI tool required)
