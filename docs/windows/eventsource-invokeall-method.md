---
title: Метод EventSource::InvokeAll | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::InvokeAll
dev_langs:
- C++
helpviewer_keywords:
- InvokeAll method
ms.assetid: 1506618f-0421-4428-a4d0-4ea2b10a3bf6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 57450abdef0a6b25731405e092520ec5589972a1
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613739"
---
# <a name="eventsourceinvokeall-method"></a>Метод EventSource::InvokeAll

Вызывает каждый обработчик событий, связанных с текущим [EventSource](../windows/eventsource-class.md) объекта, используя указанным типам аргументов и аргументы.

## <a name="syntax"></a>Синтаксис

```cpp
void InvokeAll();
template <
   typename T0
>
void InvokeAll(
   T0arg0
);
template <
   typename T0,
   typename T1
>
void InvokeAll(
   T0arg0,
   T1arg1
);
template <
   typename T0,
   typename T1,
   typename T2
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8,
   typename T9
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8,
   T9arg9
);
```

### <a name="parameters"></a>Параметры

*T0*  
Тип нулевого аргумента обработчика событий.

*T1*  
Тип первого аргумента обработчика событий.

*T2*  
Тип второго аргумента обработчика событий.

*T3*  
Тип третьего аргумента обработчика событий.

*T4*  
Тип четвертого аргумента обработчика событий.

*T5*  
Тип пятого аргумента обработчика событий.

*T6*  
Тип шестого аргумента обработчика событий.

*T7*  
Тип седьмого аргумента обработчика событий.

*T8*  
Тип восьмого аргумента обработчика событий.

*T9*  
Тип девятого аргумента обработчика событий.

*заполнитель с номером 0*  
Нулевой аргумент обработчика событий.

*arg1*  
Первый аргумент обработчика событий.

*Arg2*  
Второй аргумент обработчика событий.

*arg3*  
Третий аргумент обработчика событий.

*arg4*  
Четвертый аргумент обработчика событий.

*arg5*  
Пятый аргумент обработчика событий.

*arg6*  
Шестой аргумент обработчика событий.

*arg7*  
Седьмой аргумент обработчика событий.

*arg8*  
Восьмой аргумент обработчика событий.

*arg9*  
Девятый аргумент обработчика событий.

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также
[Класс EventSource](../windows/eventsource-class.md)