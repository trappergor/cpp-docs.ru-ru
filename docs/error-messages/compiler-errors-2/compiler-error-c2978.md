---
title: Ошибка компилятора C2978
ms.date: 11/04/2016
f1_keywords:
- C2978
helpviewer_keywords:
- C2978
ms.assetid: 5e7bee82-e266-4ccd-ad2e-ee89606ec5bf
ms.openlocfilehash: cf682bf14246754cca74a43dffc39761ff6125c1
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58780305"
---
# <a name="compiler-error-c2978"></a>Ошибка компилятора C2978

синтаксическая ошибка: требуется "ключевое_слово1" или "ключевое_слово2"; обнаружен тип "ключевое_слово3"; параметры, не являющиеся параметрами типа, не поддерживаются в универсальных классах

Универсальный класс был объявлен неправильно. См. в разделе [универсальные шаблоны](../../extensions/generics-cpp-component-extensions.md)Дополнительные сведения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2978:

```
// C2978.cpp
// compile with: /clr /c
generic <ref class T>   // C2978
// try the following line instead
// generic <typename T>   // OK
ref class Utils {
   static void sort(T elems, size_t size);
};

generic <int>
// try the following line instead
// generic <class T>
ref class Utils2 {
   static void sort(T elems, size_t size);
};
```