---
title: Импорт данных с помощью объявления __declspec(dllimport)
description: Использование __declspec (dllimport) для импорта данных библиотеки DLL.
ms.date: 09/03/2020
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
ms.openlocfilehash: cb9850306d6e73b88e2926a6f068ae21f8d32530
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609114"
---
# <a name="importing-data-using-__declspecdllimport"></a>Импорт данных с помощью `__declspec(dllimport)`

В случае с данными использование **`__declspec(dllimport)`** является удобным приемом, который позволяет устранить косвенное обращение. При импорте данных из библиотеки DLL в любом случае необходимо обращаться к таблице адресов импорта. До появления **`__declspec(dllimport)`** это означало, что при доступе к данным, экспортируемым из библиотеки DLL, обязательно требовалось дополнительное косвенное обращение:

```C
// project.h
// Define PROJECT_EXPORTS when building your DLL
#ifdef PROJECT_EXPORTS   // If accessing the data from inside the DLL
   ULONG ulDataInDll;

#else         // If accessing the data from outside the DLL
   ULONG *ulDataInDll;
#endif
```

Затем вы экспортировали данные в файл DEF:

```DEF
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   CONSTANT
```

и получали к ним доступ за пределами библиотеки DLL:

```C
if (*ulDataInDll == 0L)
{
   // Do stuff here
}
```

Если данные помечаются как **`__declspec(dllimport)`** , компилятор автоматически создает код косвенного обращения. Вам не нужно беспокоиться об описанных выше действиях. Как уже отмечалось ранее, не используйте объявление **`__declspec(dllimport)`** для данных при сборке библиотеки DLL. Функции в библиотеке DLL не используют таблицу адресов импорта для доступа к объекту данных. Таким образом, вы избежите лишнего уровня косвенного обращения.

Чтобы экспортировать данные из библиотеки DLL автоматически, используйте следующее объявление:

```C
// project.h
// Define PROJECT_EXPORTS when building your DLL
#ifdef PROJECT_EXPORTS   // If accessing the data from inside the DLL
   __declspec(dllexport) ULONG ulDataInDLL;

#else         // If accessing the data from outside the DLL
   __declspec(dllimport) ULONG ulDataInDLL;
#endif
```

## <a name="see-also"></a>См. также

[Импорт в приложение](importing-into-an-application.md)
