---
title: "Метод EventSource::InvokeAll | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource::InvokeAll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InvokeAll - метод"
ms.assetid: 1506618f-0421-4428-a4d0-4ea2b10a3bf6
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Метод EventSource::InvokeAll
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вызывает каждый обработчик событий, связанных с текущим [EventSource](../windows/eventsource-class.md) объекта с помощью указанным типам аргументов и аргументов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `T0`  
 Тип нулевого аргумента обработчика событий.  
  
 `T1`  
 Тип первого аргумента обработчика событий.  
  
 `T2`  
 Тип второго аргумента обработчика событий.  
  
 `T3`  
 Тип третьего аргумента обработчика событий.  
  
 `T4`  
 Тип четвертого аргумента обработчика событий.  
  
 `T5`  
 Тип пятого аргумента обработчика событий.  
  
 `T6`  
 Тип шестого аргумента обработчика событий.  
  
 `T7`  
 Тип седьмого аргумента обработчика событий.  
  
 `T8`  
 Тип восьмого аргумента обработчика событий.  
  
 `T9`  
 Тип девятого аргумента обработчика событий.  
  
 `arg0`  
 Нулевой аргумент обработчика событий.  
  
 `arg1`  
 Первый аргумент обработчика событий.  
  
 `arg2`  
 Второй аргумент обработчика событий.  
  
 `arg3`  
 Третий аргумент обработчика событий.  
  
 `arg4`  
 Четвертый аргумент обработчика событий.  
  
 `arg5`  
 Пятый аргумент обработчика событий.  
  
 `arg6`  
 Шестой аргумент обработчика событий.  
  
 `arg7`  
 Седьмой аргумент обработчика событий.  
  
 `arg8`  
 Восьмой аргумент обработчика событий.  
  
 `arg9`  
 Девятый аргумент обработчика событий.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс EventSource](../windows/eventsource-class.md)