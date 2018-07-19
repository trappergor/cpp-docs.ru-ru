---
title: Метод WeakRef::As | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::As
dev_langs:
- C++
helpviewer_keywords:
- As method
ms.assetid: 7173da62-b3fe-44d6-aea4-1aa97e69b221
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 70e694b4c86194402f48d335aac353e48c3de79a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890707"
---
# <a name="weakrefas-method"></a>Метод WeakRef::As
Задает определенный указатель ComPtr для представления указанного интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
template<typename U>  
HRESULT As(  
   _Out_ ComPtr<U>* ptr  
);  
  
template<typename U>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `U`  
 Идентификатор интерфейса.  
  
 `ptr`  
 Когда эта операция завершается, объект, представляющий параметр `U`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
-   Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на причину неудачного завершения операции, а `ptr` устанавливается в значение `nullptr`.  
  
-   Значение S_ОК, если операция завершилась успешно, но текущий объект WeakRef уже был выпущен. Параметр `ptr` устанавливается в значение `nullptr`.  
  
-   Значение S_OK, если операция завершилась успешно, но текущий объект WeakRef не получен из параметра `U`. Параметр `ptr` устанавливается в значение `nullptr`.  
  
## <a name="remarks"></a>Примечания  
 Если параметр `U` представляет собой IWeakReference или не получен из IInspectable, возникает ошибка.  
  
 Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../cpp/auto-cpp.md) .  
  
 Начиная с пакета SDK для Windows 10 этот метод не устанавливает экземпляр WeakRef в значение `nullptr` , если не удалось получить слабую ссылку, поэтому следует избегать использования кода проверки ошибок, который проверяет наличие `nullptr`для WeakRef. Вместо этого проверьте `ptr` для `nullptr`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс WeakRef](../windows/weakref-class.md)