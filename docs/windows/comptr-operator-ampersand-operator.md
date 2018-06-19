---
title: ComPtr::operator&amp; оператор | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0bfe8cf9091d888c33420f53f584ca5509d80527
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872410"
---
# <a name="comptroperatoramp-operator"></a>ComPtr::operator&amp; оператор
Освобождает интерфейс, связанный с этим объектом `ComPtr`, а затем извлекает адрес объекта `ComPtr`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Слабая ссылка на текущий объект `ComPtr`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод отличается от [ComPtr::GetAddressOf](../windows/comptr-getaddressof-method.md) в том, что данный метод освобождает ссылку на указатель интерфейса. Используйте метод `ComPtr::GetAddressOf`, если необходим адрес указателя интерфейса, но этот интерфейс освобождать не требуется.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)