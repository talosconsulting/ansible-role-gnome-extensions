lordtaytertot.gnome_extensions
==============================

Manages GNOME Extensions using the newer `gnome-extensions` command

Requirements
------------

[GNOME](https://www.gnome.org/) 50+

GNOME Shell only discovers extensions when it starts. If the user is logged in
when the role installs a new extension, the extension is marked as enabled but
does not load until they log out and back in.

GNOME extensions install per-user under `~/.local/share/gnome-shell/extensions/`,
so this role must be run as the desktop user — **not** as `root`. Use
`become_user` (or run the play unprivileged) to target the correct account:

```yaml
- hosts: localhost
  become: true
  become_user: alice
  roles:
    - lordtaytertot.gnome_extensions
```

Role Variables
--------------

`gnome_extension_ids`: list of GNOME Extension IDs to be installed

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: lordtaytertot.gnome_extensions, gnome_extension_ids: [ 517, 5470 ] }
```

License
-------

MIT
