---
title: Перевод типов и членов в разряд нерекомендуемых (C++/CX)
ms.date: 12/30/2016
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
ms.openlocfilehash: 6d61b00690cc087c3baced6d96d0b6c8d73b5850
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040331"
---
# <a name="deprecating-types-and-members-ccx"></a>Перевод типов и членов в разряд нерекомендуемых (C++/CX)

В C++/CX поддерживается нерекомендуемая поддержка типов среда выполнения Windows и членов для поставщиков и потребителей с использованием [устаревшего](/uwp/api/windows.foundation.metadata.deprecatedattribute) атрибута. При использовании элемента API, к которому был применен этот атрибут, вы получите предупреждение времени компиляции, в котором указывается, что данный элемент является нерекомендуемым и предлагается альтернатива. В собственных открытых типах и методах вы можете применять этот атрибут с заданием своего сообщения.

> [!CAUTION]
> [Устаревший](/uwp/api/windows.foundation.metadata.deprecatedattribute) атрибут предназначен для использования только с типами среда выполнения Windows. Для стандартных классов и членов C++ используйте [__declspec(deprecated)](../cpp/deprecated-cpp.md).

### <a name="example"></a>Пример

В следующем примере показано, как переводить в число нерекомендуемых собственные открытые API, например в компоненте среды выполнения Windows. Второй параметр, имеющий тип [Windows:Foundation::Metadata::DeprecationType](/uwp/api/windows.foundation.metadata.deprecationtype) , определяет, переводится элемент API в число нерекомендуемых или удаляется. В настоящее время поддерживается только значение DeprecationType::Deprecated. Третий параметр в атрибуте определяет платформу [Windows::Foundation::Metadata::Platform](/uwp/api/windows.foundation.metadata.platformattribute) , к которой применяется атрибут.

```

namespace wfm = Windows::Foundation::Metadata;

public ref class Bicycle sealed
{

public:
    property double Speed;

    [wfm::Deprecated("Use the Speed property to compute the angular speed of the wheel", wfm::DeprecationType::Deprecate, 0x0)]
    double ComputeAngularVelocity();
};
```

## <a name="supported-targets"></a>Поддерживаемые целевые объекты

В следующей таблице перечислены конструкции, к которым может применяться атрибут Deprecated:

:::row:::
   :::column span="":::
      см
      получить
      перечисления
      Поле перечисления \
      журнале
      interface
   :::column-end:::
   :::column span="":::
      Method
      параметризованный конструктор \
      свойство\
      struct
      поле структуры \
      элемент управления XAML
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>См. также раздел

[Система типов](../cppcx/type-system-c-cx.md)<br/>
[Справочник по языку C++/CX](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)
