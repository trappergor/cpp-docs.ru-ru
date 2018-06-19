---
title: 'Библиотек DLL расширения: Обзор | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bd851b9335e2b1ecffc8873590f176d7ebb2205
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367824"
---
# <a name="mfc-extension-dlls-overview"></a>Библиотека DLL-расширения MFC: Обзор
Расширения MFC DLL является библиотекой DLL, обычно реализуют классы многократного использования, производные от существующих классов библиотеки Microsoft Foundation Class. Библиотеки DLL расширения MFC строятся с помощью версии библиотеки MFC (также известный как общая версия MFC). Только исполняемые файлы MFC (приложения или обычные библиотеки DLL MFC), которые создаются с общедоступной версии MFC можно использовать расширения MFC DLL. С расширением MFC библиотеки DLL можно создать новые пользовательские классы из MFC и затем применять эту расширенную версию для MFC для приложений, которые вызывают библиотеку DLL.  
  
 Библиотеки DLL расширения также может использоваться для передачи объекты, производные от приложения и библиотеки DLL. Функции-члены, связанные с переданный объект существует в модуле, в котором был создан объект. Поскольку эти функции соответствующим образом экспортируются при использовании общедоступной версии библиотеки DLL MFC, можно свободно передавать MFC или MFC-производный объект указатели между приложением и библиотеки DLL, он загружает расширения MFC.  
  
 Пример библиотеки DLL, которая соответствует основным требованиям библиотеки DLL расширения MFC см. в образце MFC [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk). В частности просмотрите файлы Testdll1.cpp и Testdll2.cpp.  
  
 Обратите внимание, что термин AFXDLL больше не используется в документации Visual C++. Расширения MFC DLL имеет те же характеристики, что и прежние AFXDLL.  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Инициализация библиотеки DLL расширения MFC](../build/run-time-library-behavior.md#initializing-extension-dlls)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Библиотеки DLL расширений MFC](../build/extension-dlls.md)  
  
-   [Использование библиотек DLL расширений MFC для баз данных, OLE и сокетов в обычных DLL-библиотеках MFC](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [Общие сведения о библиотеках DLL, не являющихся MFC](../build/non-mfc-dlls-overview.md)  
  
-   [Обычные библиотеки DLL MFC, статически компонуемые с MFC](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Обычные библиотеки DLL MFC, динамически компонуемые с MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Создание библиотеки DLL MFC](../mfc/reference/mfc-dll-wizard.md)  
  
## <a name="see-also"></a>См. также  
 [Типы библиотек DLL](../build/kinds-of-dlls.md)