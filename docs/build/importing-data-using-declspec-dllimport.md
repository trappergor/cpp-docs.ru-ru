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
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440457"
---
# <a name="importing-data-using-__declspecdllimport"></a>Импорт данных с помощью объявления __declspec(dllimport)

В случае с данными использование **__declspec (dllimport)** — это удобный элемент, который удаляет уровень косвенного обращения. При импорте данных из библиотеки DLL все равно необходимо пройти по таблице адресов импорта. До **__declspec (dllimport)** это означало необходимость выполнения дополнительного уровня косвенного обращения при доступе к данным, экспортированным из библиотеки DLL:

```
// project.h
#ifdef _DLL   // If accessing the data from inside the DLL
   ULONG ulDataInDll;

#else         // If accessing the data from outside the DLL
   ULONG *ulDataInDll;
#endif
```

Затем необходимо экспортировать данные в. DEF — файл:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   CONSTANT
```

и получить к нему доступ за пределами библиотеки DLL:

```
if (*ulDataInDll == 0L)
{
   // Do stuff here
}
```

Если данные помечаются как **__declspec (dllimport)** , компилятор автоматически создает код косвенного обращения. Больше не нужно беспокоиться о действиях, описанных выше. Как упоминалось ранее, не используйте объявление **__declspec (dllimport)** для данных при сборке библиотеки DLL. Функции в библиотеке DLL не используют таблицу адресов импорта для доступа к объекту данных; Таким образом, у вас не будет дополнительного уровня косвенного обращения.

Чтобы экспортировать данные автоматически из библиотеки DLL, используйте следующее объявление:

```
__declspec(dllexport) ULONG ulDataInDLL;
```

## <a name="see-also"></a>См. также раздел

[Импорт в приложение](importing-into-an-application.md)
