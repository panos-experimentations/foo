# private package test

## in your private package:

- in `https://github.com/panos-zamos/foo.git` repository
- in `composer.json` set

```json
{
    "autoload": {
        "psr-4": {
            "Panos\\Foo\\": "src/"
        }
    }
}
```

and use `Panos\Foo` as root namespace

## then on repo where you would use your private package:

add `repositories` segment to your `composer.json` like:

```json
{
    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/panos-zamos/foo.git"
        }
    ]
}
```

and then add `"panos-zamos/foo": "dev-master"` to your require segment in your `composer.json` and run `composer update`.

> that shoud be it :)

