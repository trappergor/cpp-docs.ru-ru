---
title: синхронизировать | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.synchronize
dev_langs:
- C++
helpviewer_keywords:
- synchronize attribute
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dc056b59bc2d98ab4dcee030024e6f4a4b883dfe
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448003"
---
# <a name="synchronize"></a>synchronize

Синхронизирует доступ к целевому методу.

## <a name="syntax"></a>Синтаксис

```cpp
[synchronize]
```

## <a name="remarks"></a>Примечания

**Синхронизировать** атрибут C++ реализует поддержку для синхронизации целевого метода объекта. Синхронизация позволяет несколько объектов для использования общих ресурсов (например, метод класса) с помощью управления доступом целевого метода.

Код, вставленный в данном атрибуте вызывает соответствующую `Lock` метод (определяется по модели потоков) в начале целевой метод. При выходе из метода, `Unlock` вызывается автоматически. Дополнительные сведения об этих функциях см. в разделе [CComAutoThreadModule::Lock](../atl/reference/ccomautothreadmodule-class.md#lock)

Этот атрибут требует, чтобы атрибут [coclass](../windows/coclass.md), [progid](../windows/progid.md)или [vi_progid](../windows/vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например если `progid` применяется, `vi_progid` и `coclass` также применяются.

## <a name="example"></a>Пример

Следующий код обеспечивает синхронизацию для `UpdateBalance` метод `CMyClass` объекта.

```cpp
// cpp_attr_ref_synchronize.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module(name="SYNC")];

[coclass,
threading(both),
vi_progid("MyProject.MyClass"),
progid("MyProject.MyClass.1"),
uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")  
]
class CMyClass {
   float m_nBalance;

   [synchronize]
   void UpdateBalance(float nAdjust) {
      m_nBalance += nAdjust;
   }
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод класса, метод|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Один или несколько из следующих: `coclass`, `progid`, или `vi_progid`.|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты COM](../windows/com-attributes.md)  