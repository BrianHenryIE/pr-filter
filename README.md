[![PHP 7.2](https://img.shields.io/badge/PHP-7.2-8892BF.svg?logo=php)](https://php.net)

# PR Filter

Filter checkstyle.xml according to a diff

## Usage

```bash
phpcs -q --report=checkstyle | sponge phpcs-checkstyle.xml
git diff main > main.diff
vendor/bin/prf filter-checkstyle main.diff phpcs-checkstyle.xml filtered-checkstyle.xml --base-path=$(pwd)
```

### Options

`prf filter-checkstyle [-b|--base-path=] diff infile [outfile]`

| Argument             |    | Description                                               |
|----------------------|---------|-----------------------------------------------------------|
| `--base-path`        | `-b`    | If set, will be removed from paths in checkstyle.xml      |
| positional, required | diff    | Path to diff file         |
| positional, required | infile  | Path to checkstyle.xml to be filtered                     |
| positional, optional | outfile | Path to filtered checkstyle.xml, or will overwrite infile |
