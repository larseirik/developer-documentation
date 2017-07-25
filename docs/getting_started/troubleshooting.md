1.  [Developer](index.html)
2.  [Documentation](Documentation_31429504.html)
3.  [Get Started with eZ Platform](Get-Started-with-eZ-Platform_31429520.html)
4.  [Step 1: Installation](31429538.html)

# Avoiding Problems 

Created by Dominika Kurek, last modified by David Christian Liedle on Aug 18, 2016

WORK-IN-PROGRESS

This page will list many potential problems and gotchas that you may encounter while installing, configuring, and running eZ Platform. If you stumble upon an obstacle, take a look here to see if your case isn't covered. Want to add to this page? Check out our instructions for [contributing to our documentation](https://doc.ez.no/display/DEVELOPER/Contribute+to+Documentation).

## Enable Swap on Systems with Limited RAM

If you're having difficulty completing installation on a system with limited RAM (1GB or 2GB, for example), check that you've enabled swap. This allows your Operating System to use the hard disk to supplement RAM when it runs out. Running \``php -d memory_limit=-1 app/console ezplatform:install --env prod clean`\` on a system with swap enabled should yield success. When a system runs out of RAM, you may see \`Killed\` when trying to clear the cache (e.g., \`php app/console --env=prod cache:clear\` from your project's root directory).

## Upload Size Limit

To make use of PlatformUI, you need to define the maximum upload sizeto be consistent with the maximum file size defined in the Content Type using a File, Media or Image Field Definition.

This is done by setting `LimitRequestBody` for Apache or` client_max_body_size` for Nginx.

For instance, if one of those Field definitions is configured to accept files up to 10MB, then `client_max_body_size` (in case of Nginx) should be set above 10MB, with a safe margin, for example to 15MB.

## Initial Install Options

If you accepted all the defaults when doing a \`composer install\`, but realize you need to go back and change some of those options, look in \`app/config/parameters.yml\` – that's where they're stored.

 





