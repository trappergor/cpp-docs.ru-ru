---
title: Конструктор WeakRef::WeakRef | Документы Microsoft
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
ms.openlocfilehash: ae70dabdd86fedf82c26c0c7d9a09d842e2310e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891052"
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