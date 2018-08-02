---
title: Определения и объявления (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d192234a2b3cd3d72bef15e11678ebc41ccede0
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462892"
---
# <a name="definitions-and-declarations-c"></a>Определения и объявления (C++)
**Системам Microsoft** интерфейс DLL относится ко всем элементам (функциям и данным), про которые известно экспортироваться некоторой программой в системе, то есть все элементы, которые объявляются как **dllimport** или **dllexport** . Всех объявлениях, включенных в интерфейс DLL необходимо указать либо **dllimport** или **dllexport** атрибута. Тем не менее, в определении должен указываться только **dllexport** атрибута. Например, следующее определение функции вызовет ошибку компилятора.

```
__declspec( dllimport ) int func() {   // Error; dllimport
                                       // prohibited on definition.
   return 1;  
}
```

 Показанный ниже код также вызовет ошибку.

```
__declspec( dllimport ) int i = 10;  // Error; this is a definition.
```

 Однако следующий синтаксис правильный.

```
__declspec( dllexport ) int i = 10;  // Okay--export definition
```

 Использование **dllexport** подразумевает определение, хотя **dllimport** — объявление. Необходимо использовать **extern** ключевого слова with **dllexport** для обеспечения объявления; в противном случае подразумевается определение. Таким образом, приведенные ниже примеры правильны.

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

extern DllExport int k; // These are both correct and imply a
DllImport int j;        // declaration.
```

 В следующих примерах поясняются предшествующие.

```
static __declspec( dllimport ) int l; // Error; not declared extern.

void func() {
    static __declspec( dllimport ) int s;  // Error; not declared
                                           // extern.
    __declspec( dllimport ) int m;         // Okay; this is a
                                           // declaration.
    __declspec( dllexport ) int n;         // Error; implies external
                                           // definition in local scope.
    extern __declspec( dllimport ) int i;  // Okay; this is a
                                           // declaration.
    extern __declspec( dllexport ) int k;  // Okay; extern implies
                                           // declaration.
    __declspec( dllexport ) int x = 5;     // Error; implies external
                                           // definition in local scope.
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)