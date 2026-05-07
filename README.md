lordtaytertot.gnome-extensions
==============================

Manages GNOME Extensions using the newer `gnome-extensions` command

Requirements
------------

[GNOME](https://www.gnome.org/) 50+

GNOME extensions install per-user under `~/.local/share/gnome-shell/extensions/`,
so this role must be run as the desktop user — **not** as `root`. Use
`become_user` (or run the play unprivileged) to target the correct account:

```yaml
- hosts: localhost
  become: true
  become_user: alice
  roles:
    - lordtaytertot.gnome-extensions
```

Role Variables
--------------

`gnome_extension_ids`: list of GNOME Extension IDs to be installed

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: lordtaytertot.gnome-extensions, gnome_extension_ids: [ 517, 5470 ] }
```

License
-------

MIT
