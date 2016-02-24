Installs homebrew on OSX, manages packages, and manages cask applications.

Requirements

Role Variables

Available variables are listed below, along with default values:

homebrew_install_path: /usr/local
homebrew_brew_bin_path: /usr/local/bin

base_homebrew_packages: []
group_homebrew_packages: []
user_homebrew_packages: []

homebrew_installed_packages: "{{ base_homebrew_packages + group_homebrew_packages + user_homebrew_packages }}"

homebrew_upgrade_all_packages: no

homebrew_taps:
  - caskroom/cask

base_homebrew_cask_apps: []
group_homebrew_cask_apps: []
user_homebrew_cask_apps: []

homebrew_cask_apps: "{{ base_homebrew_cask_apps + group_homebrew_cask_apps + user_homebrew_cask_apps }}"

homebrew_cask_appdir: /Applications
Dependencies

Example Playbook

- hosts: all
  roles:
    - { role: jeremyltn.homebrew }
License

MIT

Credits

Based on https://github.com/geerlingguy/ansible-role-homebrew for osxstrap. Uses install method found at https://github.com/dirn/ansible-homebrew/blob/master/tasks/main.yml to fix errors when /usr/local already exists.
