# moodle-cookbook

This cookbook provides an LWRP for Moodle instances. It is currently geared
towards CentOS using nginx and php-fpm, but pull requests adding support for
other platforms, webservers, etc. are welcome!

## Supported Platforms

CentOS

## Attributes

The Moodle cookbook does not have any attributes of its own, but it does set a
few attributes for the nginx and php-fpm cookbooks in order to make them work
smoothly.

## Usage

```
moodle "/var/www/moodle" do
  server_name "moodle.example.com"
  create_db_and_user false
  passwordsaltmain some_salt
  passwordsalt1 some_more_salt
  dbrootpass "supersecretpass"
end
```

You are responsible for making sure the webroot ("/var/www/moodle" in this example)
is filled.

You can take a look at the [resource](resources/default.rb) for all of the available
attributes you can pass to the moodle resource.

The most important attributes are: dbhost, dbname, dbpass, dbrootpass,
passwordsaltmain, passwordsalt1, and server_name. You can find their defaults in
the [resource definition](resources/default.rb)

## Contributing

1. Fork the repository on Github
2. Create a named feature branch (i.e. `/user/add-new-recipe`)
3. Write your change
4. Write tests for your change (if applicable)
5. Run the tests, ensuring they all pass
6. Submit a Pull Request

## License and Authors

Author:: Oregon State University (<cookbooks@osuosl.org>)
