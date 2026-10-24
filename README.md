# Clarifile

A Qt desktop application for organizing files, selecting folders, cleaning junk files, and exploring file-shredding workflows. QML defines the interface; C++ supplies the file-system operations.

![Clarifile desktop interface](images/GUI_new.png)

## Architecture

- [main.qml](Clarifile/main.qml) composes the desktop interface.
- [main.cpp](Clarifile/main.cpp) registers the C++ objects exposed to QML.
- [fileorganizer.cpp](Clarifile/fileorganizer.cpp), [PathManager.cpp](Clarifile/PathManager.cpp), [junkcleaner.cpp](Clarifile/junkcleaner.cpp), and [fileshredder.cpp](Clarifile/fileshredder.cpp) implement file operations.
- [FileOrganizerShredder.pro](Clarifile/FileOrganizerShredder.pro) is the qmake application project.

## Build and run

1. Install Qt 6 with a desktop compiler kit and the Core, GUI, Widgets, SQL, QML, Quick, QuickDialogs2, and SVG modules used by the project.
2. Open `Clarifile/FileOrganizerShredder.pro` in Qt Creator.
3. Select your own installed kit and a fresh build directory, then build and run the application. The repository contains old local build/Qt Creator files; do not rely on their absolute paths or prebuilt outputs.

Launching the QML file alone with qmlscene does not register the C++ context objects, so use the compiled application for the complete interface.

## Trying file operations

Use a temporary folder containing disposable copies while exploring the organizer, cleaner, and shredder. Deletion changes real files. The shredding implementation does not establish a secure-erasure guarantee across SSDs, snapshots, backups, or different file systems.

This repository is an application prototype, with existing source and assets retained for development.
