---
title: Ошибка компилятора C3114 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3114
dev_langs:
- C++
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7d0e324c00c4b304deca1d2538913a88690d023
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054614"
---
# <a name="compiler-error-c3114"></a>Ошибка компилятора C3114

«аргумент»: Недопустимый именованный аргумент атрибута

Для элемента атрибута класса данных является допустимым именованный аргумент, он должен не быть помечен как `static`, `const`, или `literal`. Свойства, свойство не должно быть `static` и должен иметь get и set.

Дополнительные сведения см. в разделе [свойство](../../windows/property-cpp-component-extensions.md) и [определяемые пользователем атрибуты](../../windows/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3114.

```
// C3114.cpp
// compile with: /clr /c
public ref class A : System::Attribute {
public:
   static property int StaticProp {
      int get();
   }

   property int Prop2 {
      int get();
      void set(int i);
   }
};

[A(StaticProp=123)]   // C3114
public ref class R {};

[A(Prop2=123)]   // OK
public ref class S {};
```