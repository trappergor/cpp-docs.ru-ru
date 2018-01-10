---
title: "Определения и объявления (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7391180ca83d40e6ec00688054223b2e9af48e4f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="definitions-and-declarations-c"></a>Определения и объявления (C++)
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft
 Интерфейс DLL относится ко всем элементам (функциям и данным), которые заведомо экспортироваться некоторой программой в системе; то есть все элементы, которые были объявлены как `dllimport` или `dllexport`. Всех объявлениях, включенных в интерфейсе DLL необходимо указать либо `dllimport` или `dllexport` атрибута. Однако в определении должен указываться только атрибут `dllexport`. Например, следующее определение функции вызовет ошибку компилятора.

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

 Использование `dllexport` подразумевает определение, пока `dllimport` — объявление. Для обеспечения объявления ключевое слово `extern` следует использовать с аргументом `dllexport`; в противном случае подразумевается определение. Таким образом, приведенные ниже примеры правильны.

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
