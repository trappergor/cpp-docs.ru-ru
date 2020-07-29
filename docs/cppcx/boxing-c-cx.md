---
title: Упаковка-преобразование (C++/CX)
ms.date: 12/30/2016
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
ms.openlocfilehash: 59c7f8ec56a912ed993316fba093b87bd85e16b1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233539"
---
# <a name="boxing-ccx"></a>Упаковка-преобразование (C++/CX)

*Упаковка* обтекает переменную типа значения, например [Windows:: Foundation::D атетиме](/uwp/api/windows.foundation.datetime), или фундаментальный скалярный тип, такой как **`int`** , в классе ссылки, когда переменная передается в метод, принимающий [Platform:: Object ^](../cppcx/platform-object-class.md) в качестве входного типа.

## <a name="passing-a-value-type-to-an-object-parameter"></a>Передача типа значения параметру Object^

Хотя явным образом упаковывать переменную для ее передачи в параметр метода типа [Platform::Object^](../cppcx/platform-object-class.md)не требуется, необходимо выполнять явное приведение к исходному типу при получении значений, которые до этого были упакованы.

[!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]

### <a name="using-platformiboxt-to-support-nullable-value-types"></a>Использование Platform:: IBox \<T> для поддержки типов значений, допускающих значения NULL

C# и Visual Basic поддерживают понятие типов значений, допускающих значения null. В C++/CX можно использовать `Platform::IBox<T>` тип для предоставления открытых методов, поддерживающих параметры типа значения, допускающие значение null. В следующем примере показан открытый метод C++/CX, возвращающий значение null, если вызывающий объект C# передает значение NULL для одного из аргументов.

[!code-cpp[cx_boxing#02](../cppcx/codesnippet/CPP/cx_boxing/class1.h#02)]

В клиенте XAML C# его можно использовать следующим образом:

```

// C# client code
    BoxingDemo.Class1 obj = new BoxingDemo.Class1();
    int? a = null;
    int? b = 5;
    var result = obj.Multiply(a,b); //result = null
```

## <a name="see-also"></a>См. также статью

[Система типов (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Приведение (C++/CX)](../cppcx/casting-c-cx.md)<br/>
[Справочник по языку C++/CX](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)
