# Home Assistant

## Living Room Android TV remote

The file `living-room-android-tv-remote.yaml` is a dashboard card. It controls the
Living Room Android TV through the Android Debug Bridge (ADB) integration.

The card has these parts:

- A navigation pad: Back, Home, Menu, Settings, the arrows and OK.
- Power, rewind, play/pause and fast forward buttons.
- App shortcuts for Plex, YouTube and Netflix.

The card uses only built-in cards. You do not need HACS.

### Procedure to add the card

1. Find the entity ID of the ADB media player. Go to **Settings > Devices & services > Entities**.
   Search for `LivingRoom TV AndroidTV ADB`.
2. Make sure that the entity ID is `media_player.livingroom_tv_androidtv_adb`.
   If it is different, replace all instances of this ID in the YAML file.
3. Open the dashboard at `/lovelace/living-room`.
4. Select the pencil icon (**Edit dashboard**).
5. Select **Add card**. Then select **Manual**.
6. Paste the contents of the YAML file. Then select **Save**.
7. Select **Done**.

### Test

1. Select **Home** on the card. Make sure that the TV shows the home screen.
2. Select the arrows and **OK**. Make sure that the TV cursor moves.

### Troubleshooting

- If an app button does not open the app, the app ID is not correct or the app is not installed.
  Look at the `source_list` attribute of the entity in **Developer tools > States**.
  Use a value from this list as the `source`.
- If no button operates, make sure that the entity state is not `unavailable`.
