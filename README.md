# http-serve: a command-line http server

This is an extended version of [http-server](https://www.npmjs.com/package/http-server) strengthened with a support of gzip compression and a fallback option for nonexistent routes (please see 'Available Options' section bellow for details). Together with `https` support, it make the server ideal for front-end testing purposes.

---

`http-serve` itself is a simple, zero-configuration command-line http server.  It is powerful enough for production usage, but it's simple and hackable enough to be used for testing, local development, and learning.

![](https://github.com/dkarmalita/http-serve/raw/master/screenshots/public.png)


# Installing

Installation globally via `npm`:

     npm i -g http-serve

This will install `http-serve` globally so that it may be run from the command line.

Or it can be installed locally, for a project:

     npm i -D http-serve


## Usage:

     http-serve [path] [options]

`[path]` defaults to `./public` if the folder exists, and `./` otherwise.


## Usage

### Starting http-serve locally

     node bin/http-serve

*Now you can visit http://localhost:8080 to view your server*

## Available Options:

`-p` Port to use (defaults to 8080)

`-a` Address to use (defaults to 0.0.0.0)

`-d` Show directory listings (defaults to 'True')

`-i` Display autoIndex (defaults to 'True')

`-g` or `--gzip` When enabled (defaults to 'False') it will serve `./public/some-file.js.gz` in place of `./public/some-file.js` when a gzipped version of the file exists and the request accepts gzip encoding.

`-e` or `--ext` Default file extension if none supplied (defaults to 'html')

`-s` or `--silent` Suppress log messages from output

`--cors` Enable CORS via the `Access-Control-Allow-Origin` header

`-o` Open browser window after starting the server

`-c` Set cache time (in seconds) for cache-control max-age header, e.g. -c10 for 10 seconds (defaults to '3600'). To disable caching, use -c-1.

`-U` or `--utc` Use UTC time format in log messages.

`-P` or `--proxy` Proxies all requests which can't be resolved locally to the given url. e.g.: -P http://someurl.com

`-S` or `--ssl` Enable https.

`-C` or `--cert` Path to ssl cert file (default: cert.pem).

`-K` or `--key` Path to ssl key file (default: key.pem).

`-r` or `--robots` Provide a /robots.txt (whose content defaults to 'User-agent: *\nDisallow: /')
`-f` or `--fallback` Provide a fallback url if response returns 404 - useful for SPA frameworks

`-h` or `--help` Print this list and exit.

## Example

    http-serve ./dist --gzip -p /

It will run the http server for `./dist` content dirctory, with gzip commpression suport. All of the nonexistent routes will be redirected to the host's root - `/`.
