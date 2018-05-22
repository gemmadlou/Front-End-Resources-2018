According to https://wpengine.co.uk/support/how-to-change-a-multi-site-primary-domain/, 5 places in the database need updating:

* wp_options: options named “siteurl” and “home”
* wp_site
* wp_sitemeta: the option named “siteurl”
* wp_blogs: any entries in the “domains” column that have the old domain name
* wp_#_options: Each sub-site will have sets of tables that correspond to the blog_id in the wp_blogs table. You need to go to the wp_#_options table, where # corresponds to the blog_id, and update the “siteurl” and “home” settings in that table.

update wp_options set option_value='http://kisumu.thebignorth.com/wordpress' where option_name='home';

update wp_options set option_value='http://kisumu.thebignorth.com/wordpress' where option_name='siteurl';

update wp_site set domain='kisumu.thebignorth.com' where id=1;

update wp_sitemeta set meta_value='http://kisumu.thebignorth.com/wordpress/' where site_id = 1 and meta_key = 'siteurl';

update wp_blogs set domain='kisumu.thebignorth.com' where site_id=1 and blog_id=1;

