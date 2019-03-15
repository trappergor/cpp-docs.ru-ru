---
title: Импорт данных с помощью объявления __declspec(dllimport)
ms.date: 11/04/2016
f1_keywords:
- dllimport
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
ms.openlocfilehash: 74ad93e640a4e961f7670077227bb5c35a42c20f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818431"
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

[Импорт в приложение](importing-into-an-application.md)
