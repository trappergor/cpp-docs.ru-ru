---
title: Определения и объявления (C++)
ms.date: 11/04/2016
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
ms.openlocfilehash: 20683f3d2e12f7ffead573cbac46fdd4e106c383
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189381"
---
# <a name="definitions-and-declarations-c"></a>Определения и объявления (C++)

**Блок, относящийся только к системам Microsoft**

Интерфейс DLL ссылается на все элементы (функции и данные), которые могут быть экспортированы какой-либо программой в системе; то есть все элементы, объявленные как **DllImport** или **dllexport**. Все объявления, входящие в интерфейс DLL, должны указывать атрибут **DllImport** или **dllexport** . Однако определение должно задавать только атрибут **dllexport** . Например, следующее определение функции вызовет ошибку компилятора.

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

Использование **dllexport** подразумевает определение, тогда как **DllImport** подразумевает объявление. Для принудительного объявления необходимо использовать ключевое слово **extern** с **dllexport** . в противном случае подразумевается определение. Таким образом, приведенные ниже примеры правильны.

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

## <a name="see-also"></a>См. также раздел

[dllexport, dllimport](../cpp/dllexport-dllimport.md)
