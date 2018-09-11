---
title: Класс RuntimeClass | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClass class
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8f6cca23834eb889ecb83d91b40861b92fe922ad
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605988"
---
# <a name="runtimeclass-class"></a>Класс RuntimeClass

Представляет класс WinRT или COM, который наследует указанных интерфейсов и предоставляет указанной среды выполнения Windows, классическую COM-модель и поддержку слабых ссылок.

Этот класс предоставляет реализацию шаблона классов WinRT и COM, предоставляющей реализацию `QueryInterface`, `AddRef`, `Release` и т.д., управляет счетчик ссылок модуля и включает поддержку фабрика класса для предоставления Активируемый объекты.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>Параметры

*classFlags*  
Необязательный параметр. Сочетание одного или нескольких [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) значений перечисления. `__WRL_CONFIGURATION_LEGACY__` Макрос можно определить таким образом, чтобы изменить значение по умолчанию classFlags для всех классов среды выполнения в проекте. Если определено, экземпляры RuntimeClass, не являются гибкими по умолчанию. Если не определен, RuntimeClass экземпляры являются гибкими по умолчанию. Чтобы избежать неоднозначности всегда указывайте `Microsoft::WRL::FtmBase` в `TInterfaces` или `RuntimeClassType::InhibitFtmBase`. Обратите внимание, если InhibitFtmBase и FtmBase, как использовать объект будет agile.

*TInterfaces*  
Список интерфейсов, реализуемых объектом за пределами `IUnknown`, `IInspectable` или других интерфейсов, которые управляются [RuntimeClassType](../windows/runtimeclasstype-enumeration.md). Он также может перечислять других классов, производный от, в частности `Microsoft::WRL::FtmBase` сделать объект гибкой и вызвать его, чтобы реализовать `IMarshal`.

## <a name="members"></a>Участники

`RuntimeClassInitialize` Функция, которая инициализирует объект, если `MakeAndInitialize` функция-шаблон используется для создания объекта. Возвращается значение S_OK, если объект успешно инициализирован, или код ошибки COM. Если не удалось инициализировать. Код ошибки COM. распространяется как возвращаемое значение `MakeAndInitialize`. Обратите внимание, что `RuntimeClassInitialize` метод не вызывается, если `Make` функция-шаблон используется для создания объекта.

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Конструктор RuntimeClass::RuntimeClass](../windows/runtimeclass-runtimeclass-constructor.md)|Инициализирует текущий экземпляр класса RuntimeClass.|
|[Деструктор RuntimeClass::~RuntimeClass](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|Деинициализирует текущий экземпляр класса RuntimeClass.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

Это деталь реализации.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)