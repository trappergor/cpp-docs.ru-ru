---
title: Библиотеки DLL расширения. Обзор
ms.date: 05/06/2019
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
ms.openlocfilehash: ea8e950e28907ea1a4a85c1f39392d5505f08c49
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221371"
---
# <a name="mfc-extension-dlls-overview"></a>Библиотеки DLL для расширения MFC: Обзор

Библиотеки DLL расширения MFC — это библиотеки DLL, которые обычно реализуют классы многократного использования в существующих библиотеках классов Microsoft Foundation Class. Библиотеки DLL расширения MFC создаются с помощью библиотеки динамической компоновки MFC (также известной как общая версия MFC). Только исполняемые файлы MFC (приложения или обычные библиотеки DLL MFC), созданные с помощью общей версии MFC, могут использовать библиотеку DLL расширения MFC. С помощью библиотеки DLL расширения MFC можно создавать новые пользовательские классы из MFC, а затем предоставлять эту расширенную версию MFC приложениям, которые вызывают библиотеку DLL.

Библиотеки DLL расширения также можно использовать для передачи объектов, производных от MFC, между приложением и библиотекой DLL. Функции элементов, связанные с переданным объектом, существуют в модуле, в котором был создан объект. Поскольку эти функции должны быть правильно экспортированы при использовании общей версии библиотеки MFC, можно свободно передавать указатели на объекты, производные от MFC или MFC, между приложением и загружаемыми библиотеками DLL расширения MFC.

Пример библиотеки DLL, удовлетворяющей базовым требованиям библиотеки DLL расширения MFC, см. в примере MFC [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk). В частности, обратите внимание на файлы Testdll1.cpp и Testdll2.cpp.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Инициализация библиотеки DLL расширения MFC](run-time-library-behavior.md#initializing-extension-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Библиотеки DLL расширений MFC](extension-dlls.md)

- [Использование библиотек DLL расширений MFC для баз данных, OLE и сокетов в обычных DLL-библиотеках MFC](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [Несовместимые с MFC библиотеки DLL: обзор](non-mfc-dlls-overview.md)

- [Обычные библиотеки DLL MFC, статически связанные с MFC](regular-dlls-statically-linked-to-mfc.md)

- [Обычные библиотеки DLL MFC, динамически связанные с MFC](regular-dlls-dynamically-linked-to-mfc.md)

- [Создание библиотеки DLL MFC](../mfc/reference/mfc-dll-wizard.md)

## <a name="see-also"></a>См. также

[Типы библиотек DLL](kinds-of-dlls.md)
