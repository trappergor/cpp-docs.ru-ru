---
title: Импорт данных с помощью объявления __declspec(dllimport) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a024d7488eb1683f40548839ab843da1e56f65e8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710220"
---
# <a name="importing-data-using-declspecdllimport"></a>Импорт данных с помощью объявления __declspec(dllimport)

В случае данных с помощью **__declspec(dllimport)** — это элемент удобства, удаляет уровень косвенного обращения. При импорте данных из библиотеки DLL, необходимо по-прежнему проходить через таблицу адресов импорта. Прежде чем **__declspec(dllimport)**, это означало, что необходимо сделать дополнительный уровень косвенного обращения при доступе к данным из библиотеки DLL:

```
// project.h
#ifdef _DLL   // If accessing the data from inside the DLL
   ULONG ulDataInDll;

#else         // If accessing the data from outside the DLL
   ULONG *ulDataInDll;
#endif
```

Необходимо выполнить экспорт данных в вашей. DEF-файл:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   CONSTANT
```

и получить к нему доступ вне библиотеки DLL:

```
if (*ulDataInDll == 0L)
{
   // Do stuff here
}
```

Если пометить данные в виде **__declspec(dllimport)**, компилятор автоматически создает код косвенного обращения для вас. Вы больше не нужно беспокоиться о описанные выше действия. Как уже говорилось ранее, не следует использовать **__declspec(dllimport)** объявления данных при построении библиотеки DLL. В этой библиотеке DLL не используют таблицу адресов импорта для доступа к объекту данных; Таким образом вы не получите дополнительный уровень косвенного обращения.

Чтобы автоматически экспортировать данные из библиотеки DLL, используйте следующее объявление:

```
__declspec(dllexport) ULONG ulDataInDLL;
```

## <a name="see-also"></a>См. также

[Импорт в приложение](../build/importing-into-an-application.md)