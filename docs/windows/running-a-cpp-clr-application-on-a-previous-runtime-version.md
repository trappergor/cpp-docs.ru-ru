---
title: Выполнение приложения C++ с параметром -clr в более ранней версии среды выполнения
ms.date: 11/04/2016
helpviewer_keywords:
- applications [C++], runtime version specified
- versions [C++]
- app.config files, runtime version specified
- compatibility [C++], runtime version specified
- backward compatibility [C++], runtime version specified
- application deployment [C++], runtime version specified
- common language runtime [C++], version specified
- deploying applications [C++], runtime version specified
ms.assetid: 940171b7-6937-4b14-8e87-c199e23f4f2e
ms.openlocfilehash: 9b26439d389cb4035541cedde8a5b5cf50682098
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58786480"
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>Выполнение приложения C++ с параметром /clr в более ранней версии среды выполнения

Если не указано иное, приложение .NET Framework на C++ предназначено для запуска в версии среды CLR, используемой компилятором для сборки приложения. Однако приложение EXE, созданное для одной версии среды выполнения, может запускаться в другой версии, если она предоставляет необходимые функции.

Для этого предоставьте файл app.config с информацией о версии среды выполнения в теге `supportedRuntime`.

Во время выполнения имя файла app.config должно иметь формат *имя_файла.расширение*.config, где *имя_файла.расширение* — это имя исполняемого файла, запустившего приложение, а сам этот файл должен находиться в одном каталоге с исполняемым файлом. Например, если приложение называется TestApp.exe, файл app.config будет называться TestApp.exe.config.

Если указано несколько версий среды выполнения и приложение выполняется на компьютере с несколькими установленными версиями среды выполнения, приложение использует первую версию, которая указана в файле конфигурации и установлена.

## <a name="see-also"></a>См. также

[Развертывание классических приложений](deploying-native-desktop-applications-visual-cpp.md)
