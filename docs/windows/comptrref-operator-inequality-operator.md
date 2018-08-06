---
title: ComPtrRef::operator! =-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator!=
dev_langs:
- C++
ms.assetid: ab3093cc-6fbd-4039-890a-6df1cde992b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7ebe71706ce1091ee21fc6fbd63e65b201c096b5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462928"
---
# <a name="comptrrefoperator-operator"></a>Оператор ComPtrRef::operator!=
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator!=(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *a*  
 Ссылку на **ComPtrRef** объекта.  
  
 *b*  
 Ссылка на другой **ComPtrRef** объект или указатель на анонимный объект (`void*`).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Первый оператор возвращает **true** Если объект *a* не равен объекту *b*; в противном случае **false**.  
  
 Второй и третий операторы возвращают **true** Если объект *a* не равно **nullptr**; в противном случае **false**.  
  
 Четвертый и пятый операторы yield **true** Если объект *a* не равен объекту *b*; в противном случае **false**.  
  
## <a name="remarks"></a>Примечания  
 Указывает ли два **ComPtrRef** объекты не равны.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::wrl:: Details](../windows/microsoft-wrl-details-namespace.md)   
 [Класс ComPtrRef](../windows/comptrref-class.md)