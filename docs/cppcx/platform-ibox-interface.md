---
title: Интерфейс Platform::IBox | Документы Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
dev_langs:
- C++
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7894eceb2f345303400eec9b0490db58b3c3583f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089527"
---
# <a name="platformibox-interface"></a>Интерфейс Platform::IBox
[Platform::IBox](../cppcx/platform-ibox-interface.md) — это имя C++ для интерфейса `Windows::Foundation::IReference` .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template <typename T>  
interface class IBox  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Введите запакованное значение.  
  
### <a name="remarks"></a>Примечания  
 Интерфейс `IBox<T>` в основном используется внутри кода для представления типов значений, допускающих значение null, как описано в разделе [Классы и структуры значения (C++/CX)](../cppcx/value-classes-and-structs-c-cx.md). Этот интерфейс также используется для упаковки типов значений, передаваемых в методы C++, которые принимают параметры типа `Object^`. Можно в явном виде определить входной параметр как `IBox<SomeValueType>`. Пример см. в разделе [упаковка-преобразование](../cppcx/boxing-c-cx.md).  
  
### <a name="requirements"></a>Требования  
  
### <a name="members"></a>Участники  
 Интерфейс `Platform::IBox` наследуется от интерфейса [Platform::IValueType](../cppcx/platform-ivaluetype-interface.md) . Интерфейс`IBox` содержит следующие члены:  
  
 **Свойства**  
  
|Метод|Описание|  
|------------|-----------------|  
|[Значение](#value)|Возвращает распакованное значение, которое ранее хранилось в этом экземпляре `IBox` .|  

## <a name="value"></a> Свойство IBox::Value
Возвращает значение, которое было изначально сохранено в этом объекте.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
property T Value {T get();}  
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Введите запакованное значение.  
  
### <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 Возвращает значение, которое было изначально сохранено в этом объекте.  
  
### <a name="remarks"></a>Примечания  
 Пример см. в разделе [упаковка-преобразование](../cppcx/boxing-c-cx.md).  
  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)