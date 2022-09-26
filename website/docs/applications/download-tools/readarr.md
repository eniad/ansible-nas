# Readarr
Homepage: [readarr](https://readarr.com/)

**Readarr** is is a ebook collection manager for Usenet and BitTorrent users.

## Usage

Set `readarr_enabled: true` in your `/inventories/[my inventory]/group_vars/nas.yml` file.

The Readarr web interface can be found at `http://ansible_nas_host_or_ip:7878` by default

## Specific Configuration

**First make sure Readarr has permissions to write and read the `/download`, and `/books` folders**. Do this by ensuring the `readarr_books_directory:` and `readarr_download_directory` settings are correct.

Readarr will get the file path from the Download client. On default settings with Transmission the path is `/storage/downloads/complete`. You will need to create a path mapping in the **Remote Path Mappings** settings under **Download Client**  to point to your internal path that is by default `/downloads`.  *If you have difficulties with the path mapping you could also just add a new volume path for the Transmission container and use `/downloads` as the download directory.*

For Readarr to understand that the `/books` folder is a folder, you'll need to add a new subfolder into it.
You can also do this by adding a random movie to the folder. Keep in mind to have the internal setting **Create empty movie folders** on **yes**

Comprehensive setup information can be found on the [Readarr GitHub wiki](https://github.com/Readarr/Readarr/wiki/Setup-Guide)
