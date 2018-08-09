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
ms.openlocfilehash: 6e7b7d35fd8cae44c3f374a81cae572e4c9ee4f8
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011163"
---
# <a name="weakrefweakref-constructor"></a>Конструктор WeakRef::WeakRef
Инициализирует новый экземпляр класса **WeakRef** класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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