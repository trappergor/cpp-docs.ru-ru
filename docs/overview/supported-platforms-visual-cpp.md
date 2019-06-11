---
title: Поддерживаемые платформы (Visual C++)
ms.date: 05/14/2019
ms.technology: cpp-tools
helpviewer_keywords:
- Visual C++, platforms supported
- platforms [C++]
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 950f62b4cbf1255af97f1f4950bab03c58c2ceba
ms.sourcegitcommit: bde3279f70432f819018df74923a8bb895636f81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2019
ms.locfileid: "66174852"
---
# <a name="supported-platforms-visual-c"></a>Поддерживаемые платформы (Visual C++)

Приложения, разработанные с помощью Visual Studio, могут быть нацелены на различные платформы, указанные ниже.

|Операционная система|x86|X64|ARM|ARM64\*\*\*\*|
|----------------------|---------|---------|---------|---------|
|Windows XP|X\*|X\*|||
|Windows Server 2003|X\*|X\*|||
|Windows Vista|X|X|||
|Windows Server 2008|X|X|||
|Windows 7|X|X|||
|Windows Server 2012 R2|X|X|||
|Windows 8|X|X|X||
|Windows 8.1|X|X|X||
|Windows 10|X|X|X|X|
|Android \*\*|X|X|X|X|
|iOS \*\*|X|X|X|X|
|Linux \*\*\*|X|X|X|X|

\* Вы можете использовать набор инструментов платформы Windows XP, включенный в Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 и Visual Studio 2012 с обновлением 1 или более позднюю версию для создания проектов Windows XP и Windows Server 2003. Сведения об использовании этого набора инструментов платформы см. в разделе [Настройка программ для Windows XP](../build/configuring-programs-for-windows-xp.md). Дополнительные сведения о смене набора инструментов платформы: [Практическое руководство. Изменение требуемой версии .NET Framework и набора средств платформы](../build/how-to-modify-the-target-framework-and-platform-toolset.md).

\*\* Вы можете установить рабочую нагрузку **Разработка мобильных приложений на языке C++** в установщике для Visual Studio 2017 и более поздних версий. При настройке Visual Studio 2015 выберите дополнительный компонент **Visual C++ для кроссплатформенной мобильной разработки**, чтобы выбрать целевую платформу iOS или Android. Инструкции см. в разделе [Установка Visual C++ для разработки кроссплатформенных мобильных приложений](/visualstudio/cross-platform/install-visual-cpp-for-cross-platform-mobile-development). Для создания кода iOS необходимо иметь компьютер Mac и выполнить другие требованиям. Список необходимых условий и инструкции для установки см. в разделе [Установка и настройка средств для разработки с помощью iOS](/visualstudio/cross-platform/install-and-configure-tools-to-build-using-ios). Вы можете создавать код x86 или ARM для соответствия целевому оборудованию. Используйте конфигурацию x86 для создания кода для имитатора iOS, Microsoft Visual Studio Emulator для Android и некоторых устройств Android. Используйте конфигурацию ARM для создания кода для устройств iOS и большинства устройств Android.

\*\*\* Можно установить рабочую нагрузку **Разработка для Linux на C++** в установщике для Visual Studio 2017, чтобы выбрать целевую платформу Linux. Инструкции см. в разделе [Загрузка, установка и настройка рабочей нагрузки Linux](../linux/download-install-and-setup-the-linux-development-workload.md). Этот набор инструментов компилирует исполняемый файл на целевом компьютере, поэтому вы можете создавать решения для любой поддерживаемой архитектуры.

\*\*\*\* Поддержка ARM64 доступна в Visual Studio 2017 и более поздних версиях.

Сведения о том, как задать конфигурацию целевой платформы: [Практическое руководство. Настройка проектов Visual C++ для 64-разрядных платформ с архитектурой x64](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).

## <a name="see-also"></a>См. также

- [Инструменты и функции Visual C++ в выпусках Visual Studio](visual-cpp-tools-and-features-in-visual-studio-editions.md)
- [Начало работы](/visualstudio/ide/getting-started-with-cpp-in-visual-studio)
