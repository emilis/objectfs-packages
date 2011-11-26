# ObjectFS package catalog

This is a list of `package.json` files for CommonJS packages that are usable in ObjectFS.

It is used by ObjectFS package manager `ofs-pkg`.

## To add your package to the list:

- fork this repository on GitHub,
- copy `package.json` file from your package into `objectfs-packages/json/<y>/<yourpackage>.json`,
- commit changes to your fork,
- send a pull request from your fork page on GitHub.

## package.json format:

For full documentation see: <http://wiki.commonjs.org/wiki/Packages/1.1>

### Properties required by ofs-pkg:

- url of a publicly readable git repository,
- ObjectFS uri mappings for modules (if your package provides storage wrappers).

Example from [objectfs-core.json](https://github.com/emilis/objectfs-packages/blob/master/json/o/objectfs-core.json):

```json
{
  ...
  "repositories": [
    { "type":"git", "url":"git://github.com/emilis/objectfs-core.git" }],
  ...
  "objectfs-uris": [
    { "scheme":"csv", "module":"objectfs-core/wrappers/csv" },
    { "path": "*.csv", "module":"objectfs-core/wrappers/csv" }],
  ...
}
```

      
