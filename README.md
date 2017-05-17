# Protocol Implementation Generator

The goal of this project is to generate an implementation of packet template interfaces,
based on the protocol version used. This allows for a clean, multi-protocol support for
plugins to use without accessing NMS or Forge. It will use either [Mixins](https://github.com/SpongePowered/Mixin) or
Reflection to access the existing protocol versions packet classes and wrap the methods defined in the templates.
Changes in packets resulting in field type changes will result in more than one getter and setter for such a field.
These annotated fields will be generated differently depending on the targeted protocol version, but will exist on any version
and will provide warning as well as return an empty optional in most cases. This will be provided as a gradle plugin and
can be used inside any plugin or library.

Currently this is being designed to target protocol version 316 and 317. Others may be added later on, or you may add it
yourself through a PR.

This is inspired by [Sponges Event Implementation Generator](https://github.com/SpongePowered/event-impl-gen).

## Credits:

 - Connor Hartley <vectrix>