# Vodafone K5161h on TP-Link TL-WR902AC V4

The **Vodafone-branded K5161h** is basically a Huawei 4G USB modem, but it presents itself differently over USB than the normal/unbranded variants that the **TP-Link TL-WR902AC V4** expects.

Because of that, the WR902AC may show the modem as:

```text
Unplugged
```

even though the modem itself works fine.

The fix is to upload a small custom modem profile so the TP-Link knows how to switch the Vodafone version into its normal network mode.

## Installation

1. Put the physical switch on the WR902AC to:

```text
Share ETH
```

2. Open the TP-Link web interface.

3. Set the router to:

```text
3G/4G Router
```

4. Go to the **3G/4G modem settings**.

5. Choose **Add New** / **Add Modem Configuration**.

6. Upload:

```text
Vodafone-K5161h-TPLINK.bin
```

7. Save/apply the configuration.

8. Unplug the K5161h from the router and plug it back in.

The modem should now be detected instead of showing **Unplugged**.

## SIM PIN

Disable the SIM PIN before using the modem in the router.

When the modem is plugged directly into a computer, its Vodafone/Huawei interface is normally available at:

```text
http://192.168.9.1
```

Use that interface to disable SIM PIN verification.

## What the profile changes

The Vodafone K5161h initially identifies itself as:

```text
12d1:1f1d
```

and needs to be switched into:

```text
12d1:1591
```

The custom TP-Link modem profile performs that switch automatically.

## Tested with

```text
Modem:  Vodafone K5161h
Router: TP-Link TL-WR902AC V4
```

This is an unofficial compatibility fix. Other firmware or hardware revisions may behave differently.
