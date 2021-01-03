# Ansible Role: EmuELEC SMB

Easily configure SMB shares for [EmuELEC][0] using Ansible.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`).

## Example Usage

Setup a new project with an inventory file pointing to your EmuELEC setup and create a new file `main.yml` with the following contents, customised to your needs.

```yaml
- hosts: all
  become: true
  vars:
    smb_host_path: my_smb_share/games
    smb_v3: true
    smb_username: rom_user
    smb_password: rom_pass # Best use vault to keep this secure
    rom_map: 
    - { rom_dir: 'snes', smb_dir: 'SNES'}
    - { rom_dir: 'nes', smb_dir: 'NES'}
    - { rom_dir: 'dreamcast', smb_dir: 'Dreamcast'}
    - { rom_dir: 'psx', smb_dir: 'PSX'}
    - { rom_dir: 'megadrive', smb_dir: 'Sega Mega Drive'}
    - { rom_dir: 'psp', smb_dir: 'PSP'}
    - { rom_dir: 'gb', smb_dir: 'GB'}
    - { rom_dir: 'gbc', smb_dir: 'GBC'}
    - { rom_dir: 'gba', smb_dir: 'GBA'}
    - { rom_dir: 'n64', smb_dir: 'N64'}
    - { rom_dir: 'neogeo', smb_dir: 'NeoGeo'}
  roles:
    - emuelec_smb
```

```bash
ansible-playbook -i emuelec main.yml
```

## Licence 

MIT

[0]: https://github.com/EmuELEC/EmuELEC
