---
title: Перевод типов и членов в разряд нерекомендуемых (C++/CX)
ms.date: 12/30/2016
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
ms.openlocfilehash: 6cd880af7e206b4c7338e53615594ec2c65c59fc
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740502"
---
# <a name="deprecating-types-and-members-ccx"></a>Перевод типов и членов в разряд нерекомендуемых (C++/CX)

В C++языке/CX поддерживается устаревшая поддержка типов Среда выполнения Windows и членов для поставщиков и потребителей с использованием [устаревшего](/uwp/api/windows.foundation.metadata.deprecatedattribute) атрибута. При использовании элемента API, к которому был применен этот атрибут, вы получите предупреждение времени компиляции, в котором указывается, что данный элемент является нерекомендуемым и предлагается альтернатива. В собственных открытых типах и методах вы можете применять этот атрибут с заданием своего сообщения.

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

| |
|-|
|элемент управления XAML|
|delegate|
|событие|
|поле перечисления|
|перечисление|
|struct|
|метод|
|class|
|интерфейс|
|свойство;|
|поле структуры|
|параметризованный конструктор|

## <a name="see-also"></a>См. также

[Система типов](../cppcx/type-system-c-cx.md)<br/>
[Справочник по языку C++/CX](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)
