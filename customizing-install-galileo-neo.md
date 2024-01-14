## Changes to customizing the install process

The EndeavourOS install can be customized in many ways as described in the EndeavourOS wiki.<br>
Customization has been slightly changed in **Galileo neo** (January 2024).

In **Galileo neo** file `user_commands.bash` (that could be used for customization with the previous ISOs) can be split into two separate files:

- `user-commands-before.bash` which is called before starting the calamares installer.
   It gets the install mode (`offline`, `online`) as the only parameter.
- "new" `user_commands.bash` which is called near the end of the calamares execution.
   It gets the newly created user name as the only parameter. So it can be used pretty much like before.

The purpose if the split was to clearly separate the two customization phases. And it should make customization features easier to understand and use.

Note that this change is backwards compatible, i.e. the existing `user_commands.bash` should still work as expected.<br>
The old way in `user_commands.bash` will be deprecated later, so current users of the customizing feature are advised to do the split of `user_commands.bash` into the two files described above.

The new ISOs will include templates of these files in the $HOME folder of the ISO.
