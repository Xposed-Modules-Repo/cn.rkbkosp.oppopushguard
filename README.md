# OPPO Push Guard

OPPO Push Guard blocks notifications posted by non-system apps through OPPO Push's `push_oplus_category_content` content and marketing channel.

## Scope and behavior

The module hooks Android's notification service in the LSPosed **System Framework** scope. It blocks only the exact channel ID above for apps that are not system or updated-system apps. Other notification channels and system apps are unaffected. It does not change saved notification-channel settings.

The module records hook counts, block counts, and lookup errors only. Notification titles, text, and identifiers are not logged. If package lookup fails, the notification is allowed through.

## Compatibility status

The hook signatures were checked against Ace3 ColorOS 16.0.5.1002 system files and read-only framework files from a PJE110 device running `16.0.5.701(CN01)`. Three matching notification enqueue overloads were found. Device installation, runtime behavior, reboot persistence, and recovery have not yet been verified. ROM updates and other devices require separate compatibility checks.

## Install and recover

1. Download and install the APK from [Releases](https://github.com/Xposed-Modules-Repo/cn.rkbkosp.oppopushguard/releases).
2. Enable OPPO Push Guard in LSPosed and select **System Framework** only.
3. Reboot the device.

To restore normal behavior, disable the module in LSPosed and reboot. The module does not modify the system image or persist channel changes.

## Source and support

Source, build instructions, and release automation: https://github.com/rkbkosp/cn.rkbkosp.oppopushguard
