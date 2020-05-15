---
title: Импорт данных с помощью объявления __declspec(dllimport)
ms.date: 11/04/2016
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
ms.openlocfilehash: c9dce798572a91bcb9721f022393abb669970131
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440457"
---
# <a name="importing-data-using-__declspecdllimport"></a>Импорт данных с помощью объявления __declspec(dllimport)

В случае с данными использование **__declspec(dllimport)** является удобным приемом, который позволяет устранить косвенное обращение. При импорте данных из библиотеки DLL в любом случае необходимо обращаться к таблице адресов импорта. До появления **__declspec(dllimport)** это означало, что при доступе к данным, экспортируемым из библиотеки DLL, обязательно требовалось дополнительное косвенное обращение.

```
// project.h
#ifdef _DLL   // If accessing the data from inside the DLL
   ULONG ulDataInDll;

#else         // If accessing the data from outside the DLL
   ULONG *ulDataInDll;
#endif
```

Затем вы экспортировали данные в файл DEF:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   CONSTANT
```

и получали к ним доступ за пределами библиотеки DLL:

```
if (*ulDataInDll == 0L)
{
   // Do stuff here
}
```

Если данные помечаются как **__declspec(dllimport)** , компилятор автоматически создает код косвенного обращения. Вам не нужно беспокоиться об описанных выше действиях. Как уже отмечалось ранее, не используйте объявление **__declspec(dllimport)** для данных при сборке библиотеки DLL. Функции в библиотеке DLL не используют таблицу адресов импорта для доступа к объекту данных. Таким образом, вы избежите лишнего уровня косвенного обращения.

Чтобы экспортировать данные из библиотеки DLL автоматически, используйте следующее объявление:

```
__declspec(dllexport) ULONG ulDataInDLL;
```

## <a name="see-also"></a>См. также

[Импорт в приложение](importing-into-an-application.md)
