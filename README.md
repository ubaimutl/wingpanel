# Wingpanel
This version of Wingpanel, an extensible top panel for Pantheon, includes an auto-hide feature that allows it to behave similarly to the macOS top bar. It is a fork modified to work seamlessly with elementary OS 7.

Wingpanel is an empty container that accepts indicators as extensions, including the applications menu. Individual indicators are hosted in their own repositories [here](https://github.com/search?q=topic%3Awingpanel+org%3Aelementary&type=Repositories).

[![Translation status](https://l10n.elementary.io/widgets/wingpanel/-/wingpanel/svg-badge.svg)](https://l10n.elementary.io/engage/wingpanel/?utm_source=widget)

## Building and Installation

To install this version of Wingpanel, you'll need the following dependencies:

- libgala-dev
- libgee-0.8-dev
- libglib2.0-dev
- libgranite-dev >= 5.4.0
- libgtk-3-dev
- meson
- libmutter-10-dev
- valac

You can install these dependencies on Ubuntu-based systems using the command:

\```bash
sudo apt-get update
sudo apt-get install -y \
    build-essential \
    valac \
    libglib2.0-dev \
    libgee-0.8-dev \
    libgtk-3-dev \
    libwnck-3-dev \
    libgranite-dev \
    gettext \
    libmutter-10-dev \
    libmutter-cogl-10-dev \
    libmutter-cogl-pango-10-dev \
    libmutter-clutter-10-dev \
    gir1.2-mutter-10 \
    libgala-dev \
    meson
\```

After installing the dependencies, you can build and install Wingpanel using the following commands:

\```bash
meson build --prefix=/usr
cd build
ninja
sudo ninja install
io.elementary.wingpanel
\```

## Preventing Wingpanel from restarting, e.g. for development

Wingpanel is started automatically on elementary OS with `gnome-session` autostarts. If you kill the `io.elementary.wingpanel` process twice within 60 seconds, it will keep `gnome-session` from restarting it until you log out or reboot.
