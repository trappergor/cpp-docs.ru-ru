---
title: Конструктор WeakRef::WeakRef | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef, constructor
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eafbddea6ae651d74d8f33be8efa58c25a8a0d3d
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641477"
---
# <a name="weakrefweakref-constructor"></a>Конструктор WeakRef::WeakRef
Инициализирует новый экземпляр класса **WeakRef** класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WeakRef();  
WeakRef(  
   decltype(__nullptr)  
);  
  
WeakRef(  
   _In_opt_ IWeakReference* ptr  
);  
  
WeakRef(  
   const ComPtr<IWeakReference>& ptr  
);  
  
WeakRef(  
   const WeakRef& ptr  
);  
  
WeakRef(  
   _Inout_ WeakRef&& ptr  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *ptr*  
 Указатель, ссылка или rvalue ссылка на существующий объект, который инициализирует текущий **WeakRef** объекта.  
  
## <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует пустой **WeakRef** объекта. Второй конструктор инициализирует **WeakRef** объекта из указателя на `IWeakReference` интерфейс. Третий конструктор инициализирует **WeakRef** объект из ссылки на `ComPtr<IWeakReference>` объекта. Инициализирует четвертый и пятый конструкторы **WeakRef** из другого объекта **WeakRef** объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс WeakRef](../windows/weakref-class.md)