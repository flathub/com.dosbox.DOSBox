# Flatpak for DOSBox

## Installation

This Flatpak is available on
[Flathub](https://flathub.org/apps/details/com.dosbox.DOSBox).
After following the [Flatpak setup guide](https://flatpak.org/setup/),
you can install it by entering the following command in a terminal:

```bash
flatpak install flathub com.dosbox.DOSBox -y
```

Once the Flatpak is installed, you can run DOSBox using your desktop environment's
application launcher or by running `flatpak run com.dosbox.DOSBox` in a terminal.

## Updating

This Flatpak follows the latest stable DOSBox version.
To update it, run the following command in a terminal:

```bash
flatpak update
```

## Limitations

- For security reasons, this Flatpak is sandboxed and only has access to the
  user's Documents folder. You should place any files you need within DOSBox in
  that folder (or in a subfolder).

Please [create an issue](https://github.com/flathub/com.dosbox.DOSBox/issues/new)
if you find any other limitations that should be documented here.

## Configuration files

Under the default Flatpak configuration, the DOSBox configuration files are
located in `~/.var/app/com.dosbox.DOSBox/.dosbox/`. To access it with a
graphical file manager, you'll have to make hidden folders visible.

## Building from source

Install Git, follow the
[flatpak-builder setup guide](https://docs.flatpak.org/en/latest/first-build.html)
then enter the following commands in a terminal:

```bash
git clone --recursive https://github.com/flathub/com.dosbox.DOSBox.git
cd com.dosbox.DOSBox
flatpak install flathub org.freedesktop.Sdk//23.08 -y
flatpak-builder --force-clean --install --user -y builddir com.dosbox.DOSBox.json
```

If all goes well, the Flatpak will be installed after building. You can then
run it using your desktop environment's application launcher.

You can speed up incremental builds by installing [ccache](https://ccache.dev/)
and specifying `--ccache` in the flatpak-builder command line (before `builddir`).
