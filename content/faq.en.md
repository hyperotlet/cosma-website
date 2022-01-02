---
title: Frequently Asked Questions
layout: faq
---

## I tried to launch the application but my operating system won't let me.

You can ignore your operating system's warnings and run Cosma, provided you download the application from our GitHub repository, the only official source. To override system warnings, you must have administrator privileges on your session. On macOS, right-click the application then select Open (you may have to do it twice).

Explanation: Windows and macOS require that the code of an application be “signed” in order to trust it automatically. This is done by obtaining a certificate. The process is technically trivial, but is not free, because there is a lot at stake. Indeed, if an application is not signed, the system displays an alert and asks the user to confirm his intentions. Faced with this, many users prefer caution and give up. It is therefore in the best interest of application providers to sign their application so that it can be used. But the case of Cosma is particular: it is experimental research software, only recently made public, and with no dedicated funding. The application is therefore not signed.

## The alpha was available for Linux, what about version 1.0?

We do not currently provide the application for Linux but we hope to do so soon. Cosma is an Electron-based application, meaning it can be developed for several platforms simultaneously from a single code base. Right now, we just don't have Linux machines to test Cosma on. If this is something you'd like to help us with, please get in touch!

## I tried creating a record but the application responds with a cryptic error.

You probably did not set a records directory in Preferences. Cosma needs to know where to create records.

[An issue has been opened on GitHub](https://github.com/graphlab-fr/cosma/issues/6). An upcoming update will improve the user experience on this point.

## I created a record with the same name as an existing one, and the old one is gone!

[An issue has been opened on GitHub](https://github.com/graphlab-fr/cosma/issues/5). This will be fixed in the upcoming update.

Don't forget to backup your data, either by making copies at regular intervals or by using a version control system such as [git](https://git-scm.com).

## Do I really need to use unique identifiers? Can't I link my records via their titles?

No. Using unique identifiers reduces the risk of dead links without requiring automated maintenance. We feel very strongly about this choice.

### But 14-digit links are so cumbersome…

Cosma allows you to replace the 14-digit identifiers by an arbitrary string in the output (cosmoscope). In [the demo](/demo.html), we chose to replace them with a simple arrow (→) but you could use a pointing hand (☞) or any other Unicode string. In Cosma, click on Preferences and enter the substitute character(s) in Link Symbol.

## Is it possible to manage multiple directories?

We plan to make this easily possible via a dedicated menu in a future update. In the meantime, it is *technically possible* to do it by following the suggestions below.

### Method 1: History

This method is based on the history. It works well for cosmoscopes that you do not intend to modify, and with automatic history disabled.

Imagine you have two directories, `dir1` and `dir2`:

- In Cosma, set the application to `dir1`. Click on History and then manually save the cosmoscope and give it a description. Close the history.
- Next, set the application to `dir2`. Click on History and then manually save the cosmoscope and give it a description. Close the history.

You can now switch between cosmoscopes by clicking on View History, select the desired history entry, Open.

### Method 2: `config.json

This method requires manual juggling of configuration files.

Locate the directory containing the files necessary for the proper functioning of the Cosma application (hereafter referred to as the "support directory"). This depends on the operating system:

- on macOS: `your user name/Library/Application Support/cosma` ;
- on Windows: `C:/Users/login/AppData/Roaming/cosma` ;

In this directory you will find a `config.json` file. This is where Cosma stores and retrieves the configuration.

Again, imagine you have two directories, `dir1` and `dir2`:

- In Cosma, configure the application for the `dir1` directory. Then locate the `config.json` file in the support directory and make a copy elsewhere. We advise you to create a dedicated directory, e.g. `Cosma Configurations`, with a subdirectory `dir1` and copy `config.json` into it.
- Back in Cosma, configure the application for the `dir2` directory, then do the same as before: locate the `config.json` file in the support directory and copy it elsewhere, for example into a `dir2` subdirectory of the same `Cosma Configurations`.

You can now switch to a specific directory by copying the corresponding `config.json` file to the support directory. Update the Cosma display by clicking on New Cosmoscope.