---
title: Определения и объявления (C)
ms.date: 11/04/2016
helpviewer_keywords:
- export functions
ms.assetid: d150395a-89d4-4298-9ac4-08f84fe1261c
ms.openlocfilehash: 1ec42f17d22b24aac3d19a3b129babe723930ae7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620237"
---
# <a name="definitions-and-declarations-c"></a>Определения и объявления (C)

**Блок, относящийся только к системам Microsoft**

Интерфейс DLL относится ко всем элементам (функциям и данным), про которые известно, что некоторая программа в системе будет их экспортировать, т. е. ко всем элементам, объявленным как **dllimport** или `dllexport`. Во всех объявлениях, включенных в интерфейс DLL, нужно указать атрибут **dllimport** или `dllexport`. Однако определение может задавать только атрибут `dllexport`. Например, следующее определение функции вызовет ошибку компилятора.

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllImport int func()    /* Error; dllimport prohibited in */
                        /* definition. */
{
   return 1;
}
```

Показанный ниже код также вызовет ошибку.

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllImport int i = 10;      /* Error; this is a definition. */
```

Однако следующий синтаксис правильный.

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllExport int i = 10;      /* Okay: this is an export definition. */
```

Использование атрибута `dllexport` подразумевает определение, а **dllimport** — объявление. Для обеспечения объявления ключевое слово `extern` следует использовать с аргументом `dllexport`; в противном случае подразумевается определение.

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

extern DllImport int k;   /* These are correct and imply */
Dllimport int j;          /* a declaration. */
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Функции импорта и экспорта DLL](../c-language/dll-import-and-export-functions.md)