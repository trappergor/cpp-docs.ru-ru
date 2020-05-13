---
title: Пространство имен Platform::Collections
ms.date: 01/18/2018
ms.topic: reference
f1_keywords:
- collection/Platform::Collections
helpviewer_keywords:
- Platform::Collections Namespace
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
ms.openlocfilehash: ab6b78f1b88c586a11276d36387fb42ea6ee667f
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032425"
---
# <a name="platformcollections-namespace"></a>Пространство имен Platform::Collections

Платформа::Коллекции пространства имен `Map` `MapView`содержит `Vector`, `VectorView` , и классы. Эти классы являются конкретными реализациями соответствующих интерфейсов, которые определены в пространстве имен [Windows::Foundation::Collections](/uwp/api/windows.foundation.collections) . Конкретные типы коллекций не могут переноситься через интерфейс ABI (например, когда программа JavaScript или C# вызывает компонент C++), но они могут неявно преобразоваться в соответствующие типы интерфейсов. Например, если вы реализуете открытый метод, который заполняет и возвращает коллекцию, используйте [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) для внутренней реализации коллекции и [Windows::Foundation::Collections::IVector](/uwp/api/windows.foundation.collections.ivector-1) в качестве возвращаемого типа. Для получения дополнительной информации [ознакомьтесь с коллекциями](../cppcx/collections-c-cx.md) и [созданием компонентов для выполнения Windows в си-з.](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)

Можно создать Platform::Collections::Vector из [std::vector](../standard-library/vector-class.md) и [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) из [std::map](../standard-library/map-class.md).

Кроме того, Платформа::Коллекции namespace обеспечивает поддержку обратно вставки `VectorView` и ввода итераторов, и `Vector` итераторы.

Вы должны`#include`включить ( ) заголовок collection.h для использования типов в платформе::Коллекции namespace.

## <a name="syntax"></a>Синтаксис

```cpp
#include <collection.h>
using namespace Platform::Collections;
```

### <a name="members"></a>Участники

Это пространство имен содержит следующие члены.

|Имя|Описание|
|----------|-----------------|
|[Платформа:Коллекции::BackInsertIterator Класс](../cppcx/platform-collections-backinsertiterator-class.md)|Представляет итератор, который вставляет элемент в конец коллекции.|
|[Платформа:Коллекции::Класс ввода-иттератора](../cppcx/platform-collections-inputiterator-class.md)|Представляет итератор, который вставляет элемент в начало коллекции.|
|[Платформа:Коллекции::Карта класса](../cppcx/platform-collections-map-class.md)|Представляет изменяемую коллекцию пар "ключ-значение", доступ к которым можно получить по ключу. Аналогично [std::map](../standard-library/map-class.md).|
|[Класс Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md)|Представляет доступную только для чтения коллекцию пар "ключ-значение", доступ к которым можно получить по ключу.|
|[Платформа:Коллекции::Векторный класс](../cppcx/platform-collections-vector-class.md)|Представляет изменяемую последовательность элементов. Аналогично [std::vector](../standard-library/vector-class.md).|
|[Платформа:Коллекции::Вектор-класс](../cppcx/platform-collections-vectoriterator-class.md)|Представляет итератор, который обходит коллекцию `Vector` .|
|[Класс Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md)|Представляет доступную только для чтения последовательность элементов.|
|[Платформа:Коллекции::ВекторИтатор Класс](../cppcx/platform-collections-vectorviewiterator-class.md)|Представляет итератор, который обходит коллекцию `VectorView` .|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)

### <a name="requirements"></a>Требования

**Метаданные:** platform.winmd

**Пространство имен:** Platform::Collections

**Параметр компилятора:** /ZW

## <a name="see-also"></a>См. также раздел

[Название платформы](../cppcx/platform-namespace-c-cx.md)
