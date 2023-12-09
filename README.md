#  How to publish a GitHub Pages site to a custom domain from Google Domains using Cloudflare for DNS and HTTPS:
1. Set up your GitHub Repository:

    Create a GitHub repository containing your HTML, CSS, and other necessary files.

2. Enable GitHub Pages:

    Go to your GitHub repository.
    Click on the "Settings" tab.
    Scroll down to the "GitHub Pages" section.
    Choose the branch you want to publish (typically main or master).
    Set the folder, if your HTML file is not in the root directory.

3. Purchase a Domain:

    Go to Google Domains (or any other domain registrar) and purchase your desired domain.

4. Update Google Domains DNS:

    In Google Domains, go to "Manage domains."
    Click on your domain, then go to the "DNS" tab.
    Update the name servers to the ones provided by Cloudflare:
       - clarissa.ns.cloudflare.com
       - grant.ns.cloudflare.com

5. Configure DNS with Cloudflare:

    Add your domain to Cloudflare and follow the steps to set up DNS records.

        Add a CNAME record:
            Name: Your domain (e.g., example.com)
            Value: Your GitHub Pages domain (e.g., yourusername.github.io)

        Add a second CNAME record for www subdomain:
            Name: www
            Value: Your GitHub Pages domain (e.g., yourusername.github.io)

        Create A records, point your apex domain to the IP addresses.
            A @ 185.199.108.153
            A @ 185.199.109.153
            A @ 185.199.110.153
            A @ 185.199.111.153

7. Enable Cloudflare SSL:

    In Cloudflare, go to the SSL/TLS section.
    Set SSL to "Full" or "Flexible" depending on your GitHub Pages configuration.
    Go to Edge certificates and enable Always Use Https

8. Configure Custom Domain on GitHub:

    In your GitHub repository settings, enter your custom domain in the "Custom domain" field.

9. (Optional) Run a build script / action to publish the project (eg. for Astro projects)

10. Wait for DNS Propagation:

    DNS changes may take some time to propagate. Be patient and wait for it to complete.

11. Check Your Domain:

    Open a web browser and navigate to your custom domain (e.g., http://www.example.com). It may take a while for the changes to take effect.

12. Verify HTTPS:

    Ensure that your site is accessible over HTTPS. It might take some time for the SSL certificate to be issued by Cloudflare.

13. Troubleshooting:

    If there are issues, check GitHub Pages and Cloudflare settings.
    Check for any errors or warnings in the Cloudflare dashboard.

That's it! You've successfully published a GitHub Pages site to a custom domain using Cloudflare for DNS and HTTPS. Keep in mind that DNS changes might take some time to propagate, so your site may not be immediately accessible via the custom domain.
