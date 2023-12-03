# azalea-viaversion

Add multiversion support to your [Azalea](https://github.com/mat-1/azalea) bots, powered by [ViaProxy](https://github.com/ViaVersion/ViaProxy).

## Usage

To use this plugin, simply add the dependency with `cargo add azalea_viaversion --git=https://github.com/azalea-rs/azalea-viaproxy` and then add `.add_plugins(azalea_viaversion::ViaVersionPlugin::start("version name here").await)` to your `SwarmBuilder`.

Note that this plugin currently does not support `ClientBuilder` due to limitations in how `ClientBuilder` currently works.
Also, this plugin depends on the Git (unstable) version of Azalea, so make sure you're using that.

The plugin will automatically download the latest version of ViaProxy and saves it at `~/.minecraft/azalea-viaversion`.

```rs
SwarmBuilder::new()
    .set_handler(handle)
    .add_plugins(azalea_viaversion::ViaVersionPlugin::start("1.19.4").await)
    .add_account(account.clone())
    .start("localhost")
    .await;
```