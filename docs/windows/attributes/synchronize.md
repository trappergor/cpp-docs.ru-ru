---
title: Синхронизация (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 740d99bfbc0da4c290a09a95f5d4f8f227a11fc8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792192"
---
# <a name="synchronize"></a>synchronize

Синхронизирует доступ к целевому методу.

## <a name="syntax"></a>Синтаксис

```cpp
[synchronize]
```

## <a name="remarks"></a>Примечания

**Синхронизировать** атрибут C++ реализует поддержку для синхронизации целевого метода объекта. Синхронизация позволяет несколько объектов для использования общих ресурсов (например, метод класса) с помощью управления доступом целевого метода.

Код, вставленный в данном атрибуте вызывает соответствующую `Lock` метод (определяется по модели потоков) в начале целевой метод. При выходе из метода, `Unlock` вызывается автоматически. Дополнительные сведения об этих функциях см. в разделе [CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock)

Этот атрибут требует, чтобы [coclass](coclass.md), [progid](progid.md), или [vi_progid](vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например если `progid` применяется, `vi_progid` и `coclass` также применяются.

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

Дополнительные сведения о контекстах атрибутов см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты COM](com-attributes.md)  