---
title: Общие сведения о библиотеках расширения (DLL)
ms.date: 11/04/2016
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
ms.openlocfilehash: 1967370f587b0b78c4e68ebff14804b20f158bd0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498206"
---
# <a name="mfc-extension-dlls-overview"></a>Библиотеки DLL расширений MFC: Обзор

Расширения MFC DLL представляет собой библиотеку DLL, которая обычно реализуют классы многократного использования, производные от существующих классов библиотеки Microsoft Foundation Class. Библиотеки DLL расширения MFC, созданы с использованием версии библиотеки MFC (также называется общей версии MFC). Только исполняемыми приложениями MFC (приложения или обычные библиотеки DLL MFC), построенные с помощью общей версии MFC можно использовать библиотеки DLL расширения MFC. С помощью библиотеки DLL расширения MFC можно создать новые пользовательские классы из MFC и затем предложить это расширенная версия MFC, к приложениям, которые вызывают библиотеку DLL.

Библиотеки DLL расширения можно использовать также для передачи объекты, производные от приложения и библиотеки DLL. Функции-члены, связанные с переданный объект существует в модуле, в котором был создан объект. Так как эти функции экспортируются правильно при использовании общей версии библиотеки DLL MFC, можно свободно передавать MFC или MFC-производный объект указатели между приложением и библиотеки DLL, он загружает расширения MFC.

Пример библиотеки DLL, которая соответствует основным требованиям библиотеки DLL расширения MFC, см. в образце MFC [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk). В частности просмотрите файлы Testdll1.cpp и Testdll2.cpp.

Обратите внимание, что термин AFXDLL больше не используется в документации по Visual C++. Библиотеки DLL расширения MFC имеет те же характеристики, что и прежние AFXDLL.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Инициализация библиотеки DLL расширения MFC](../build/run-time-library-behavior.md#initializing-extension-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Библиотеки DLL расширений MFC](../build/extension-dlls.md)

- [Использование библиотек DLL расширений MFC для баз данных, OLE и сокетов в обычных DLL-библиотеках MFC](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [Общие сведения о библиотеках DLL, не являющихся MFC](../build/non-mfc-dlls-overview.md)

- [Обычные библиотеки DLL MFC, статически компонуемые с MFC](../build/regular-dlls-statically-linked-to-mfc.md)

- [Обычные библиотеки DLL MFC, динамически компонуемые с MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)

- [Создание библиотеки DLL MFC](../mfc/reference/mfc-dll-wizard.md)

## <a name="see-also"></a>См. также

[Типы библиотек DLL](../build/kinds-of-dlls.md)