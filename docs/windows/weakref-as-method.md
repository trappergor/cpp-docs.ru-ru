---
title: Метод WeakRef::As | Документация Майкрософт
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
ms.openlocfilehash: 7dd0dca806c1568d88c20eec6a7ac63e5fb242fb
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020360"
---
# <a name="weakrefas-method"></a>Метод WeakRef::As
Задает указанный `ComPtr` параметр-указатель для представления указанного интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename U>  
HRESULT As(  
   _Out_ ComPtr<U>* ptr  
);  
  
template<typename U>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *U*  
 Идентификатор интерфейса.  
  
 *ptr*  
 После завершения операции, объект, представляющий параметр *U*.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
-   Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину произошел сбой операции, и *ptr* присваивается **nullptr**.  
  
-   Значение S_OK, если операция завершилась успешно, но текущий **WeakRef** объект уже был выпущен. Параметр *ptr* присваивается **nullptr**.  
  
-   Значение S_OK, если операция завершилась успешно, но текущий **WeakRef** объект не является производным от параметра *U*. Параметр *ptr* присваивается **nullptr**.  
  
## <a name="remarks"></a>Примечания  
 Ошибка создается в том случае, если параметр *U* — `IWeakReference`, или не является производным от `IInspectable`.  
  
 Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../cpp/auto-cpp.md) .  
  
 Начиная с пакета SDK для Windows 10, этот метод устанавливает **WeakRef** экземпляр **nullptr** Если не удалось получить слабую ссылку, поэтому следует избегать кода проверки ошибок проверки для WeakRef **nullptr**. Вместо этого проверьте *ptr* для **nullptr**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс WeakRef](../windows/weakref-class.md)