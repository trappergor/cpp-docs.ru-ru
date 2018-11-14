---
title: Перевод типов и членов в разряд нерекомендуемых (C++/CX)
ms.date: 12/30/2016
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
ms.openlocfilehash: 1e29f2ff73d6fb6fd499052d9f9255f8b1a659c7
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51325852"
---
# <a name="deprecating-types-and-members-ccx"></a>Перевод типов и членов в разряд нерекомендуемых (C++/CX)

В C + +/ CX, прекращении типов среды выполнения Windows и члены для производителей и получателей с помощью [не рекомендуемые к использованию](/uwp/api/windows.foundation.metadata.deprecatedattribute) атрибут поддерживается. При использовании элемента API, к которому был применен этот атрибут, вы получите предупреждение времени компиляции, в котором указывается, что данный элемент является нерекомендуемым и предлагается альтернатива. В собственных открытых типах и методах вы можете применять этот атрибут с заданием своего сообщения.

> [!CAUTION]
> [Не рекомендуемые к использованию](/uwp/api/windows.foundation.metadata.deprecatedattribute) атрибут предназначен для использования только с типами среды выполнения Windows. Для стандартных классов и членов C++ используйте [__declspec(deprecated)](../cpp/deprecated-cpp.md).

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
|делегат|
|событие|
|поле перечисления|
|перечисление|
|структура|
|метод|
|класс|
|интерфейс|
|свойство;|
|поле структуры|
|параметризованный конструктор|

## <a name="see-also"></a>См. также

[Система типов](../cppcx/type-system-c-cx.md)<br/>
[Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)