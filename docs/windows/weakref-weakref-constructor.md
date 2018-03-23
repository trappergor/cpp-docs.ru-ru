---
title: Конструктор WeakRef::WeakRef | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef, constructor
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c215006412a1ab882792546e575b6f448529a652
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="weakrefweakref-constructor"></a>Конструктор WeakRef::WeakRef
Инициализирует новый экземпляр класса WeakRef.  
  
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
  
#### <a name="parameters"></a>Параметры  
 `ptr`  
 Указатель, ссылка или ссылка rvalue на существующий объект, который инициализирует текущий объект WeakRef.  
  
## <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует пустой объект WeakRef. Второй конструктор инициализирует объект WeakRef из указателя на интерфейс IWeakReference. Третий конструктор инициализирует объект WeakRef из ссылки на объект ComPtr\<IWeakReference > объекта. Четвертый и пятый конструкторы инициализирует объект WeakRef из другой объект WeakRef.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс WeakRef](../windows/weakref-class.md)